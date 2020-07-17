<template>
    <div class="appStore">
      <el-breadcrumb separator-class="el-icon-arrow-right" class="bread">
         <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
         <el-breadcrumb-item>活动管理</el-breadcrumb-item> 
         <el-breadcrumb-item>活动列表</el-breadcrumb-item>
         <el-breadcrumb-item>活动详情</el-breadcrumb-item>
      </el-breadcrumb>


      <div class="ybox">
         <div class="header">
              <search/>
              <div class="sort ymouse">
                  <span :class="{'sortActive':sortType ==0}" @click="sortType = 0">已启用</span>
                  <span style="margin:0px 5px; color:#999">|</span>
                  <span :class="{'sortActive':sortType ==1}" @click="sortType = 1">已停用</span>
              </div>
         </div>
         <div class="main">
            <div class="list">
                <appList/>
            </div>
         </div>
         <div class="footer">
               <el-pagination
                  background
                  layout="prev, pager, next"
                  :total="1000">
               </el-pagination>
         </div> 
         </div>
    </div>
</template>

<script>
import search from '../../../../components/index/app/appStore/search';
import appList from '../../../../components/index/app/myApp/appList';
export default {
    data(){
       return{
          sortType:0 // 0 最新 1 最热
          
       }
    },
    methods:{

    },
    components:{
       search,
       appList
    },
    watch:{
      sortType(e,e1){
         //  e是新的数据，e1 是旧的数据
          console.log(e,"切换最新和最热");
         //  每次根据e 发送不同的请求然后去渲染列表
         if(e==0){
            //按照最新排序

         }else{
             //按照最热排序

         }

      }
    }

}
</script>
<style lang="scss" scoped>
    @import '../../../../assets/common.scss'; 
    .appStore{
         *{
            color: $color1;
         }

         width: 100%;
         // height: 100%;
         //background:$bgColor;
         // overflow-y: scroll;
         //border: 1px solid red;
         padding: 0;
         // padding-bottom: 20px;

        .bread{
           margin: 10px 0px 20px;
         //   border: 1px solid red;
           
         }


     


         .header{
            // border: 2px solid darkblue;
            // height:80px;
            position: relative;

            .sort{
               //  border: 1px solid red;
                margin: 30px 0px;
            }

            .sortActive{
                color: $theamColor;
            }
           
         }

         .main{
            // border: 2px solid darkcyan;

            .list{

            }

          

           
         }


         .footer{
            // border: 1px solid red;
             text-align: center;
             margin-top: 50px;
         }

    }
</style>

<style>

</style>