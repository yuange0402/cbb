<template>
  <div class="wrapper">
       <!-- 头部 -->
        <div class="header">
            <userHead/>
        </div>
        <!-- 身体 --> 
        <el-row class="body">
            <!-- 左边一级菜单 -->
            <el-col :span="2"  class="left y-no-scrollBar" >
                <!-- <h5>默认颜色</h5> -->
                <el-menu
                default-active="2"
                class="el-menu-vertical-demo" 
                
                @open="handleOpen"
                @close="handleClose">
                    <el-menu-item 
                                   @click="selectFirstmenu(item.title)"
                                  v-for="(item,idx) in menuList"
                                  :key="idx" 
                                  :index="String(idx)">
                        <!-- el-icon-menu -->
                        <i :class="item.icon"></i>
                        <span slot="title">{{item.title}}</span>
                    </el-menu-item>
                </el-menu>
            </el-col>
             
            <!-- 左边的二级菜单 -->
            <el-col :span="2" class="left y-no-scrollBar" >
                <!-- <h5>默认颜色</h5> -->
                <el-menu 
                  default-active="2"
                  class="el-menu-vertical-demo" 
                >
                    <el-menu-item v-for="(item,idx) in sonMenu" 
                                  :key="idx" 
                                  :index="String(idx)"
                                  @click="selectSecondMenu(item.title)"
                                  >
                        <!-- el-icon-menu -->
                        <i :class="item.icon"></i>
                        <span slot="title">{{item.title}}</span>
                    </el-menu-item>
                </el-menu>
            </el-col>
            
            <!-- 右边列表 -->
            <el-col class="right"  :span="20">
                <nuxt/>

            </el-col>
        </el-row>
</div>
</template>
<script>
import chartTest from '@/components/echart/test'
import userHead from '@/components/index/userHead'
  export default {
      components:{
          chartTest
      }, 
      data(){
          return{
              menuList:[
                  {
                      icon:"el-icon-menu",
                      title:"概览",
                      index:1,
                  },
                  {
                      icon:"el-icon-menu",
                      title:"业务",
                       index:2
                  },
                  {
                      icon:"el-icon-menu",
                      title:"用户",
                       index:3
                  },
                  {
                      icon:"el-icon-menu",
                      title:"平台",
                       index:4
                  },
                  {
                      icon:"el-icon-menu",
                      title:"财务",
                       index:5
                  },
                  {
                      icon:"el-icon-menu",
                      title:"数据",
                       index:6
                  },
                  {
                      icon:"el-icon-menu",
                      title:"应用",
                       index:6
                  },
                   {
                      icon:"el-icon-menu",
                      title:"订单",
                       index:6
                  },
              ],

              sonMenuList:{
                  "概览":[
                      {
                            icon:"el-icon-menu",
                            title:"今日信息",
                       },
                       {
                            icon:"el-icon-menu",
                            title:"使用指南",
                       },
                  ],
                  "应用":[
                      {
                            icon:"el-icon-menu",
                            title:"已采购的应用",
                       },
                       {
                            icon:"el-icon-menu",
                            title:"应用市场",
                       },
                  ],
                  "财务":[
                      {
                            icon:"el-icon-menu",
                            title:"账户余额",
                       },
                       {
                            icon:"el-icon-menu",
                            title:"账单",
                       },
                       {
                            icon:"el-icon-menu",
                            title:"邀请收益",
                       },
                  ],
                  "数据":[
                      {
                            icon:"el-icon-menu",
                            title:"今日信息",
                       },
                       {
                            icon:"el-icon-menu",
                            title:"使用指南",
                       },
                  ],
                  "订单":[
                      {
                            icon:"el-icon-menu",
                            title:"平台订单",
                       },
                      {
                            icon:"el-icon-menu",
                            title:"用户订单",
                       },
                      
                  ],
                  
              },
              //默认使用子菜单的第一项   
              sonMenu:[
                      {
                            icon:"el-icon-menu",
                            title:"今日信息",
                       },
                       {
                            icon:"el-icon-menu",
                            title:"使用指南",
                       },
              ],
              sonMenuTitleList:[

              ]
              


          }
      },
      mounted(){
        //进入页面之后进入默认路由
          
        
        

      },
      components:{
          userHead,
      },
    methods: {
        //点击了左边的主菜单
      selectFirstmenu(e){
          //如果点击了同一个item,那么停止   
          console.log(e,"点击了一级菜单")
          //根据e获取子菜单
          this.sonMenu =  this.sonMenuList[e];  
          //改变路由，进入子菜单的第一个item的路由
          
          //根据e 的值来获取子菜单的标题,如果是控那么使用一个默认的值
          let sonTitle = this.sonMenuTitleList[e];
          if(sonTitle){
               this.sonTitle = sonTitle;
          }else{
               this.sonTitle = "菜单";
          }

         
      },
      selectSecondMenu(e){
        console.log(e,"点击了二级菜单");
        //根据e值来进入不同的路由
      },
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>
<style lang="scss" scoped>
.wrapper{
    // border:5px solid darkmagenta;
    height: 100vh;
    overflow: hidden;
    min-width: 1200px;
    // min-height: 600px;
     

    .header{
         //border: 1px solid red;
         height:$headerHeight;
         .left{
            border: 1px solid darkblue;
            height: 100%;
         }
         .right{
              border: 1px solid darkblue;
               height: 100%;
         }
    } 


    .body{
        height: 100%;
        border: 2px solid darkgreen;
        .left{



            // border: 5px solid red;
            height:calc(100vh - 100px);
            overflow: scroll;
            .el-menu-vertical-demo{
                // border: 5px solid darkgreen;
                height: 100%;
            }

        }

        .right{
              border: 1px solid red; 
              height:calc(100% - 100px);
            //   overflow: scroll; 


            //  overflow: scroll;
        }
    }
}
    
</style>
