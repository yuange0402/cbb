<template>
     <div class="confirmOrder ybox">
        <div class="msgW">
           <div class="title">应用确认订单</div>
           <div class="goodsMsg">
               <div class="nameImgW">
                   <div class="imgW">
                       <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
                   </div>
                   <div class="goodsName">商品名称</div>
               </div>
                <div class="goodsTime">6个月</div>
                <div class="price">166元</div>
           </div>
           <div class="msgList">
                <!-- <div class="msgItem">
                    <div>订单名称：</div>
                    <div>ksdlfsdf</div>
                </div> -->
                <div class="msgItem"> 
                     <div class="itemTitle"> 应用规格：</div>
                      <div class="itemValue">6个月</div>
                </div>
                <div class="msgItem">
                      <div class="itemTitle">金额合计：</div>
                       <div class="itemValue">120元</div>
                </div>
                <div class="msgItem">
                    <div class="itemTitle">优惠卷抵扣：</div>
                     <div class="itemValue">-20元</div>
                </div>
                <div class="msgItem">
                    <div class="itemTitle">应付总额：</div>
                     <div class="itemValue">100元</div>
                </div>
           </div>
           <div class="button">
               <el-button  @click="$router.back(-1)">取消</el-button>
               <el-button type="primary">提交订单</el-button>
           </div>
        </div>
     </div>
</template>

<script>
export default {

}
</script>
<style lang="scss" scoped>
    @import '../../../../assets/common.scss';
     .confirmOrder{
        //  height: 100%;
        //  overflow-y: scroll;
        color: #333;
        position: relative;

     .msgW{
        //  border: 1px solid red;
         width: 100%; 

         .title{
                font-size:18px;
                font-family:Microsoft YaHei;
                font-weight:bold;
                color:$color1;
                border-bottom: 1px solid $underlineColor;
                padding: 5px 5px 20px;

         }

         .goodsMsg{
            //  border: 1px solid red;
             display: flex;
             justify-content: space-between;
             align-items: center;
             border-bottom: 1px solid $underlineColor;
             padding: 15px 0px;

             .nameImgW{
                 display: flex;
                 align-items: center;
                 .goodsName{
                     margin-left: 20px;
                 }
                 
             }

             .imgW{
                 width:50px;
                 height:50px;
                 border-radius: 5px;
                 overflow: hidden;
                 img{
                     width: 100%;
                     height: 100%;
                 }
             }
         }


        .msgList{
            //  border: 1px solid red;
             display: flex;
             flex-direction: column;
             align-items:flex-end;
             text-align: right;
             border-bottom: 1px solid $underlineColor;
             padding:10px 0px;


            .msgItem{
                        // border: 1px solid $underlineColor;
                        //  display: inline-block;
                        font-size: 14px;
                        display: flex;
                        padding:5px 0px;
                        

                .itemTitle{
                    color: #999999;
                }



                .itemValue{
                    width: 100px;
                    text-align: right;
                    color: $theamColor;
                    // border: 1px solid red;
                }
            }

         }


  


         .imgW{
              width: 200px;
              height: 200px;
              
              img{
                  width: 100%;
                  height: 100%;
              }
         }

       
        }


        .button{
            float: right;
            padding:25px 0px 0px;
        }
     }
</style>

<style>

</style>