<template>
     <div class="confirmOrder">
         <div class="msgW">
           <div class="title">title</div>
           <div class="imgW">
               <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
           </div>
           <div class="msgList">
                <div class="msgItem">
                    <div>订单名称：</div>
                    <div>ksdlfsdf</div>
                </div>
                <div class="msgItem"> 
                     <div> 应用规格：</div>
                      <div>ksdlfsdf</div>
                </div>
                <div class="msgItem">
                      <div>原价：</div>
                       <div>ksdlfsdf</div>
                </div>
                <div class="msgItem">
                    <div>优惠：</div>
                     <div>ksdlfsdf</div>
                </div>
                <div class="msgItem">
                    <div>现价：</div>
                     <div>ksdlfsdf</div>
                </div>
           </div>
           <div class="button">
               <el-button @click="$router.back(-1)">取消</el-button>
               <el-button>提交订单</el-button>
           </div>
           </div>
     </div>
</template>

<script>
export default {

}
</script>
<style lang="scss" scoped>
     .confirmOrder{
         height: 100%;
         overflow-y: scroll;

     .msgW{
         border: 5px solid red;
         width: 500px;

         .title{

         }


         .imgW{
              width: 200px;
              height: 200px;
              
              img{
                  width: 100%;
                  height: 100%;
              }
         }

         .msgList{
              border: 1px solid red;

              .msgItem{
                  display: flex;
              }
         }


     }
     }
</style>

<style>

</style>