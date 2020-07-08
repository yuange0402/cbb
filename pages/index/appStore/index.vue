<template>
    <div class="appStore">
         <div class="header">
              <search/>
              <div class="sort ymouse">
                  <span :class="{'sortActive':sortType ==0}" @click="sortType = 0">最新</span>
                  <span :class="{'sortActive':sortType ==1}" @click="sortType = 1">最热</span>
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
</template>

<script>
import search from '@/components/index/appStore/search';
import appList from '@/components/index/appStore/appList';
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
    .appStore{
         width: 100%;
         height: 100%;
         background: #999;
     


         .header{
            border: 5px solid darkblue;
            height:80px;
            position: relative;

            .sort{
                border: 1px solid red;
                position: absolute;
                bottom: 0;
                right: 0;
            }

            .sortActive{
                color: $theamColor;
            }
           
         }

         .main{
            height:calc(100% - 130px);
            border: 2px solid darkcyan;
            overflow-y: scroll;

          

           
         }


         .footer{
            border: 1px solid red;
            height:50px;
            display: flex;
            justify-content: center;
            align-items: center;
             
         }

    }
</style>

<style>

</style>