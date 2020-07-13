<template>
  <div class="wrapper">
       <!-- 头部 -->
        <div class="header">
            <div class="logo">
                 <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
            </div>

             <userHead  class="userHead"/>
              <el-button  type="primary" class="indexBtn" >
                  查看平台首页
              </el-button>
        </div>
        <!-- 身体 --> 
        <div class="body">
            <!-- 左边一级菜单 -->
            <div class="left left1" >
                <!-- <h5>默认颜色</h5> -->
                <el-menu
                    default-active="0"
                    class="el-menu-vertical-demo menu y-no-scrollBar" 
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
            </div>
             
            <!-- 左边的二级菜单 -->
            <div class="left left2">
                <div v-if = "showSecondMenu">

                        
                 <el-menu
                    default-active="0"
                    class="el-menu-vertical-demo menu y-no-scrollBar" 
                   >
                        

                        <!-- 有三级菜单 -->
                        <el-submenu index="1">
                                <template slot="title">
                                <div>● 导航一</div>
                                </template>
                        
                                <el-menu-item  index="1-1">选项1</el-menu-item>
                                <el-menu-item index="1-2">选项2</el-menu-item>
                        
                        
                        </el-submenu>



                        <!-- 没有三级菜单 -->
                        <el-menu-item 
                                  @click="selectSecondMenu(item.path)"
                                  v-for="(item,idx) in sonMenu"
                                  :key="idx" 
                                  
                                  :index="String(idx)">
                  
                                <span >●</span>
                                <span slot="title">{{item.title}}</span>
                        </el-menu-item>
                </el-menu>




                      <!-- <div class="ymenu">
                           <div class="menuItem">
                                <div class="itemTitle">概览</div>
                                <div class="itemList">
                                     <div style="font-size:5px;" v-for="item in 3" :key="item">选项{{item}}</div>
                                </div>
                           </div>
                      </div> -->
                </div>
            </div>
            
            <!-- 右边列表 -->
            <div class="right"  :span="20">
                <nuxt/>
            </div>
        </div>
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
              showSecondMenu:true,
              secondMenuIdx:'1',
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
                            path:"/overview/todayMsg"
                       },
                       {
                            icon:"el-icon-menu",
                            title:"使用指南",
                            path:"/overview/guide"
                       },
                  ],
                  "应用":[
                      {
                            icon:"el-icon-menu",
                            title:"已采购应用",
                            path:'/app/myApp'
                       },
                       {
                            icon:"el-icon-menu",
                            title:"应用市场",
                            path:'/app/appStore'
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
                            path:"/overview/todayMsg"
                       },
                       {
                            icon:"el-icon-menu",
                            title:"使用指南",
                            path:"/overview/guide"
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
          //隐藏二级菜单   
          this.showSecondMenu = false;
          //赋值
           this.sonMenu =  this.sonMenuList[e];  
           //显示二级菜单
           setTimeout(() => {
                this.showSecondMenu = true;    
           },3);
          let that = this;
          //如果点击了同一个item,那么停止
          console.log(e,"点击了一级菜单")
          //根据e 的值来获取子菜单的标题,如果是控那么使用一个默认的值
          let sonTitle = this.sonMenuTitleList[e];
          if(sonTitle){
               this.sonTitle = sonTitle;
          }else{
               this.sonTitle = "菜单";
          }

          //每次点击了一级菜单都要改变路由重新加载页面
          //进入二级菜单的第一个item
           let sonMenu = this.sonMenuList[e]
        //    console.log(sonMenu,"进入路由--------") 
           if(sonMenu&&sonMenu.length>0){
               let path = sonMenu[0].path;
               this.$router.push({
                   path,
               });
                // 二级菜单是有记忆的，所以每次都要手动设置
                // 二级菜单是第一个item
                

                // console.log(that.secondMenuIdx,"path--------") 
           }else{
               console.log("没有二级菜单=====")
           }


         
      },
      selectSecondMenu(path){
        console.log(path,"点击了二级菜单");
        //根据e值来进入不同的路由
        this.$router.push({
            path:path
        })
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
    // border:3px solid darkmagenta;
    height: 100vh;
    overflow: hidden;
    min-width: 1200px;
    padding: 0;
    //min-height: 600px;
    
     

    .header{
        //  border: 3px solid red;
         position: relative;
         height:$headerHeight;
         background-color: #fff;
         border-bottom: 1px solid $underlineColor;
         display: flex;
         align-items: center;
         .logo{
              //border: 1px solid red; 
              height: 100%;
              width: 110px;
              float: left;
              img{
                  width: 100%;
                  height: 100%;
              }
         }


         .userHead{
            //  border: 1px solid red;
             position: absolute;
             right: 0px;

          
         }



         .indexBtn{
            //  border: 1px solid darkblue;
             position: absolute;
             right:150px;
         }
        //  .left{
        //     // border: 5px solid darkblue;
        //     height: 100%;
        //  }
        //  .right{
        //       border: 1px solid darkblue;
        //       height: 100%;
        //  }
    } 


    .body{
        height: 100%;
        // border: 2px solid darkgreen;
        display: flex;

        .left1{
            background-color: #F4F6FA;
            width: 110px;
            // border: 5px solid red;
            .is-active {
                // color: #fff;
                background-color:#fff;
                
            }
        }

        .left{
            // background-color:orange;
            // border: 5px solid red;
            // background: rgba(0,0,0,0);
            // height:100%;
             height:calc(100vh - 70px);
            flex-shrink: 0;            

            .menu{
                overflow-y: scroll;
                overflow-x: hidden;
                padding-bottom: 100px;
                // border: 3px solid darkmagenta;
                width: 100%;
                height: 100%;


                .titleW{
                    text-align: center;
                }

              

              


                .el-submenu__title{
                     &>i{
                         display: none;
                     }
                     .el-submenu__icon-arrow{
                         display: none!important;
                     }
                }

            }
              



           //border: 5px solid red;
           //    overflow:scroll;
           //    overflow-x: scroll;
           .el-menu-vertical-demo{
                //border: 5px solid darkgreen;
                height: 100%;
            }

        }

        .left2{
            // border: 2px solid red;
            width:120px;
            flex-shrink: 0;
            .el-menu{
                &>.el-menu-item{
                    // text-align: center;
                }
                .el-submenu{
                    //   border: 5px solid darkblue;
                       .el-menu-item{
                          width: 100%; 
                          width: 130px!important;
                          min-width: 0!important;
                          font-size: 10px;
                      }
                }
            } 
                 
        }

        .right{
            //   border: 3px solid red; 
              height:calc(100% - 85px);
              overflow: scroll; 
              background-color:$bgColor;
              padding: 15px;
              width: 100%;
            //   padding-bottom:50px!important;

            //  overflow: scroll;
        }
    }
}
    
</style>
<style lang="scss">

        

        //修改菜单的边框
        .el-menu{
            border: none;
            // background-color: red;
            background: rgba(0,0,0,0);
            // height: 100%!important;

            .el-submenu__title i{
                display: none!important;
            }


              .el-submenu{
                    //   border: 5px solid darkblue;
                    // 
                   
                }

              

          
        }





     
</style>
<style>
  

     .el-menu-item .ytitleItem{
         font-size: 20px!important;
     }
</style>
