<template>
     <div class="pay ybox">
           <div class="title">订单支付</div>
           <div class="payMsg">
                <div class="msgLeft">
                     <div class="msgLtop">订单已提交，请您尽快付款</div> 
                     <div class="msgLbottom">商品名称： 人格的个地方</div> 
                </div>
                <div class="msgRight"></div>
           </div>
           <div class="payType">
               <div class="spec">
                   <span class="titleName">支付方式：</span>
                   <div :class="{'specChecked':specItem == 'wx','specItem':true,'ymouse':true}" @click="specItem = 'wx'">
                       <svg t="1594781036294" class="wxicon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="1626" width="25" height="25"><path d="M395.846 603.585c-3.921 1.98-7.936 2.925-12.81 2.925-10.9 0-19.791-5.85-24.764-14.625l-2.006-3.864-78.106-167.913c-0.956-1.98-0.956-3.865-0.956-5.845 0-7.83 5.928-13.68 13.863-13.68 2.965 0 5.928 0.944 8.893 2.924l91.965 64.43c6.884 3.864 14.82 6.79 23.708 6.79 4.972 0 9.85-0.945 14.822-2.926L861.71 282.479c-77.149-89.804-204.684-148.384-349.135-148.384-235.371 0-427.242 157.158-427.242 351.294 0 105.368 57.361 201.017 147.323 265.447 6.88 4.905 11.852 13.68 11.852 22.45 0 2.925-0.957 5.85-2.006 8.775-6.881 26.318-18.831 69.334-18.831 71.223-0.958 2.92-2.013 6.79-2.013 10.75 0 7.83 5.929 13.68 13.865 13.68 2.963 0 5.928-0.944 7.935-2.925l92.922-53.674c6.885-3.87 14.82-6.794 22.756-6.794 3.916 0 8.889 0.944 12.81 1.98 43.496 12.644 91.012 19.53 139.48 19.53 235.372 0 427.24-157.158 427.24-351.294 0-58.58-17.78-114.143-48.467-163.003l-491.39 280.07-2.963 1.98z" fill="#09BB07" p-id="1627"></path></svg>
                       微信支付
                       <span v-if="specItem == 'wx'" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                   </div>
                   <div :class="{'specChecked':specItem == 'zfb','specItem':true,'ymouse':true}"  @click="specItem = 'zfb'">
                        <svg t="1594781505208" class="wxicon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3093" width="25" height="25"><path d="M902.095 652.871l-250.96-84.392s19.287-28.87 39.874-85.472c20.59-56.606 23.539-87.689 23.539-87.689l-162.454-1.339v-55.487l196.739-1.387v-39.227H552.055v-89.29h-96.358v89.294H272.133v39.227l183.564-1.304v59.513h-147.24v31.079h303.064s-3.337 25.223-14.955 56.606c-11.615 31.38-23.58 58.862-23.58 58.862s-142.3-49.804-217.285-49.804c-74.985 0-166.182 30.123-175.024 117.55-8.8 87.383 42.481 134.716 114.728 152.139 72.256 17.513 138.962-0.173 197.04-28.607 58.087-28.391 115.081-92.933 115.081-92.933l292.486 142.041c-11.932 69.3-72.067 119.914-142.387 119.844H266.37c-79.714 0.078-144.392-64.483-144.466-144.194V266.374c-0.074-79.72 64.493-144.399 144.205-144.47h491.519c79.714-0.073 144.396 64.49 144.466 144.203v386.764z m-365.76-48.895s-91.302 115.262-198.879 115.262c-107.623 0-130.218-54.767-130.218-94.155 0-39.34 22.373-82.144 113.943-88.333 91.519-6.18 215.2 67.226 215.2 67.226h-0.047z" fill="#02A9F1" p-id="3094"></path></svg>
                       支付宝支付
                        <span v-if="specItem == 'zfb'" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                    </div>
               </div>
           </div>
            <div class="totalMoney">支付金额：<span>100元</span></div>
            <div class="btnW">
                 <el-button class="cancel">取消</el-button>
                 <el-button class="yprimary" type="primary">确认支付</el-button>
            </div>
     </div>
</template>

<script>
export default {
     data(){
           return{
                specItem:"wx"
           }
     }

}
</script>
<style lang="scss" scoped>
  @import '../../../../assets/common.scss';
      .pay{

          &>.title{
                  font-size:18px;
                    font-family:Microsoft YaHei;
                    font-weight:bold;
                    color:$color1;
          }

      

        .specChecked{
             &>span{
                color: $theamColor;
             }
             border: 1px solid $theamColor!important;
         }

      .payMsg{
          background:rgba(228,255,233,1);
          border-radius:6px;
          margin-top: 20px;
          padding: 10px;
          display: flex;
          justify-content: space-between;

          .msgLeft{
            //border: 1px solid red;
            //width: 50%;
 
               .msgLtop{
                    font-size:18px;
                    font-family:Microsoft YaHei;
                    font-weight:400;
                    color:rgba(29,180,57,1);

               }
          }

          .msgRight{
               // border: 1px solid red; 
               // width: 50%;
          }

          .msgLbottom{
               font-size:14px;
               font-family:Microsoft YaHei;
               font-weight:400;
               margin-top: 10px;


          }

      }


      .payType{
           margin-top: 30px;
           padding: 10px;
            border-top: 1px solid $underlineColor;
            border-bottom: 1px solid $underlineColor;
            .spec{
                    display: flex;
                    align-items: center;


                    .titleName{
                         font-size:16px;
                         font-family:Microsoft YaHei;
                         font-weight:400;

                    }
                   .specItem{
                       border: 1px solid $underlineColor;
                       margin:10px;
                       padding: 2px 15px 10px;
                       position: relative;
                       border-radius: 5px;
                       //overflow: hidden;
                         font-size:16px;
                         font-family:Microsoft YaHei;
                         font-weight:400;

                         .wxicon{
                              transform: translateY(7px);
                         }


                       .mark{
                        //    border: 1px solid red;
                           position: absolute;
                           width: 10px;
                           height: 10px;
                           right:20px;
                           bottom:13px;
                           font-size: 30px;
                       }
                   }

              }
      }




     .totalMoney{
          text-align: right;
          margin: 20px 0px;

          font-size:18px;
          font-family:Microsoft YaHei;
          font-weight:400;
          color:rgba(51,51,51,1);
 

          &>span{
                color: $theamColor;
          }
     }

     .btnW{
           text-align: right;
          //  font-size: 18px!important;
          .yprimary{
               padding:15px 40px;
               font-size: 18px;
          }

          .cancel{
               
               padding:15px 40px;
               font-size: 18px;
          }

          &>button{
               margin-left:40px;
          }
     }



      }
</style>

<style>

</style>