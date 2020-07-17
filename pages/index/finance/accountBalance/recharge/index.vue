<template>
    <div class="recharge">
          <el-breadcrumb separator-class="el-icon-arrow-right" class="ybread">
               <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
               <el-breadcrumb-item>活动管理</el-breadcrumb-item>
               <el-breadcrumb-item>活动列表</el-breadcrumb-item>
               <el-breadcrumb-item>活动详情</el-breadcrumb-item>
           </el-breadcrumb>
           <div class="ybox rechargeBox">
                 <div class="rechargeTitle">积分充值</div>
                 <div class="itemBox">
                      <div class="rLeft">积分余额：</div>
                      <div class="rRight">
                         63415 <span style="color:#999">（1元=10积分）</span>
                      </div> 
                 </div> 

                     <!-- 规格框 -->
               <div class="spec itemBox">
                   <span class="rLeft">支付方式：</span>

                   <div class="specList">
                  
                   <div :class="{'specChecked':specItem == 'wx','specItem':true,'ymouse':true}" @click="specItem = 'wx'">
                      <svg t="1594801083672" class="wxicon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2637" width="25" height="25"><path d="M789.8112 234.1888C715.5712 159.9488 616.96 119.0912 512 119.0912s-203.5712 40.8576-277.8112 115.0976S119.0912 407.04 119.0912 512s40.8576 203.5712 115.0976 277.8112S407.04 904.9088 512 904.9088s203.5712-40.8576 277.8112-115.0976S904.9088 616.96 904.9088 512s-40.8576-203.5712-115.0976-277.8112z m-68.1984 242.3808l-78.6432 76.6976L661.504 661.504c2.3552 13.9264-3.1744 27.648-14.6432 35.9424-6.4512 4.7104-14.0288 7.0656-21.6064 7.0656-5.8368 0-11.6736-1.4336-17.1008-4.3008l-97.28-51.0976-97.28 51.0976c-12.4928 6.5536-27.3408 5.5296-38.7072-2.7648-11.3664-8.2944-16.9984-22.1184-14.6432-35.9424L378.88 553.1648l-78.6432-76.6976c-10.1376-9.8304-13.7216-24.2688-9.3184-37.6832 4.4032-13.4144 15.7696-23.04 29.696-24.9856l108.6464-15.7696 48.64-98.5088c6.2464-12.6976 18.8416-20.48 32.9728-20.48 14.1312 0 26.7264 7.8848 32.9728 20.48l48.64 98.5088 108.6464 15.7696c13.9264 2.048 25.3952 11.5712 29.696 25.088 4.5056 13.312 0.9216 27.7504-9.216 37.6832z" p-id="2638" fill="#f6ef37"></path></svg>
                       500积分<br><span style="font-size:14px; color:#999">￥500</span>
                       <span v-if="specItem == 'wx'" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                   </div>
                   <div :class="{'specChecked':specItem == 'wx','specItem':true,'ymouse':true}" @click="specItem = 'wx'">
                      <svg t="1594801083672" class="wxicon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2637" width="25" height="25"><path d="M789.8112 234.1888C715.5712 159.9488 616.96 119.0912 512 119.0912s-203.5712 40.8576-277.8112 115.0976S119.0912 407.04 119.0912 512s40.8576 203.5712 115.0976 277.8112S407.04 904.9088 512 904.9088s203.5712-40.8576 277.8112-115.0976S904.9088 616.96 904.9088 512s-40.8576-203.5712-115.0976-277.8112z m-68.1984 242.3808l-78.6432 76.6976L661.504 661.504c2.3552 13.9264-3.1744 27.648-14.6432 35.9424-6.4512 4.7104-14.0288 7.0656-21.6064 7.0656-5.8368 0-11.6736-1.4336-17.1008-4.3008l-97.28-51.0976-97.28 51.0976c-12.4928 6.5536-27.3408 5.5296-38.7072-2.7648-11.3664-8.2944-16.9984-22.1184-14.6432-35.9424L378.88 553.1648l-78.6432-76.6976c-10.1376-9.8304-13.7216-24.2688-9.3184-37.6832 4.4032-13.4144 15.7696-23.04 29.696-24.9856l108.6464-15.7696 48.64-98.5088c6.2464-12.6976 18.8416-20.48 32.9728-20.48 14.1312 0 26.7264 7.8848 32.9728 20.48l48.64 98.5088 108.6464 15.7696c13.9264 2.048 25.3952 11.5712 29.696 25.088 4.5056 13.312 0.9216 27.7504-9.216 37.6832z" p-id="2638" fill="#f6ef37"></path></svg>
                       500积分<br><span style="font-size:14px; color:#999">￥500</span>
                       <span v-if="specItem == 'wx'" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                   </div>
                   <div :class="{'specChecked':specItem == 'wx','specItem':true,'ymouse':true}" @click="specItem = 'wx'">
                      <svg t="1594801083672" class="wxicon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2637" width="25" height="25"><path d="M789.8112 234.1888C715.5712 159.9488 616.96 119.0912 512 119.0912s-203.5712 40.8576-277.8112 115.0976S119.0912 407.04 119.0912 512s40.8576 203.5712 115.0976 277.8112S407.04 904.9088 512 904.9088s203.5712-40.8576 277.8112-115.0976S904.9088 616.96 904.9088 512s-40.8576-203.5712-115.0976-277.8112z m-68.1984 242.3808l-78.6432 76.6976L661.504 661.504c2.3552 13.9264-3.1744 27.648-14.6432 35.9424-6.4512 4.7104-14.0288 7.0656-21.6064 7.0656-5.8368 0-11.6736-1.4336-17.1008-4.3008l-97.28-51.0976-97.28 51.0976c-12.4928 6.5536-27.3408 5.5296-38.7072-2.7648-11.3664-8.2944-16.9984-22.1184-14.6432-35.9424L378.88 553.1648l-78.6432-76.6976c-10.1376-9.8304-13.7216-24.2688-9.3184-37.6832 4.4032-13.4144 15.7696-23.04 29.696-24.9856l108.6464-15.7696 48.64-98.5088c6.2464-12.6976 18.8416-20.48 32.9728-20.48 14.1312 0 26.7264 7.8848 32.9728 20.48l48.64 98.5088 108.6464 15.7696c13.9264 2.048 25.3952 11.5712 29.696 25.088 4.5056 13.312 0.9216 27.7504-9.216 37.6832z" p-id="2638" fill="#f6ef37"></path></svg>
                       500积分<br><span style="font-size:14px; color:#999">￥500</span>
                       <span v-if="specItem == 'wx'" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                   </div>
                   <br>
                   <div :class="{'specChecked':specItem == 'wx','specItem':true,'ymouse':true}" @click="specItem = 'wx'">
                      <svg t="1594801083672" class="wxicon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2637" width="25" height="25"><path d="M789.8112 234.1888C715.5712 159.9488 616.96 119.0912 512 119.0912s-203.5712 40.8576-277.8112 115.0976S119.0912 407.04 119.0912 512s40.8576 203.5712 115.0976 277.8112S407.04 904.9088 512 904.9088s203.5712-40.8576 277.8112-115.0976S904.9088 616.96 904.9088 512s-40.8576-203.5712-115.0976-277.8112z m-68.1984 242.3808l-78.6432 76.6976L661.504 661.504c2.3552 13.9264-3.1744 27.648-14.6432 35.9424-6.4512 4.7104-14.0288 7.0656-21.6064 7.0656-5.8368 0-11.6736-1.4336-17.1008-4.3008l-97.28-51.0976-97.28 51.0976c-12.4928 6.5536-27.3408 5.5296-38.7072-2.7648-11.3664-8.2944-16.9984-22.1184-14.6432-35.9424L378.88 553.1648l-78.6432-76.6976c-10.1376-9.8304-13.7216-24.2688-9.3184-37.6832 4.4032-13.4144 15.7696-23.04 29.696-24.9856l108.6464-15.7696 48.64-98.5088c6.2464-12.6976 18.8416-20.48 32.9728-20.48 14.1312 0 26.7264 7.8848 32.9728 20.48l48.64 98.5088 108.6464 15.7696c13.9264 2.048 25.3952 11.5712 29.696 25.088 4.5056 13.312 0.9216 27.7504-9.216 37.6832z" p-id="2638" fill="#f6ef37"></path></svg>
                       500积分<br><span style="font-size:14px; color:#999">￥500</span>
                       <span v-if="specItem == 'wx'" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                   </div>
                   <div :class="{'specChecked':specItem == 'wx','specItem':true,'ymouse':true}" @click="specItem = 'wx'">
                      <svg t="1594801083672" class="wxicon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2637" width="25" height="25"><path d="M789.8112 234.1888C715.5712 159.9488 616.96 119.0912 512 119.0912s-203.5712 40.8576-277.8112 115.0976S119.0912 407.04 119.0912 512s40.8576 203.5712 115.0976 277.8112S407.04 904.9088 512 904.9088s203.5712-40.8576 277.8112-115.0976S904.9088 616.96 904.9088 512s-40.8576-203.5712-115.0976-277.8112z m-68.1984 242.3808l-78.6432 76.6976L661.504 661.504c2.3552 13.9264-3.1744 27.648-14.6432 35.9424-6.4512 4.7104-14.0288 7.0656-21.6064 7.0656-5.8368 0-11.6736-1.4336-17.1008-4.3008l-97.28-51.0976-97.28 51.0976c-12.4928 6.5536-27.3408 5.5296-38.7072-2.7648-11.3664-8.2944-16.9984-22.1184-14.6432-35.9424L378.88 553.1648l-78.6432-76.6976c-10.1376-9.8304-13.7216-24.2688-9.3184-37.6832 4.4032-13.4144 15.7696-23.04 29.696-24.9856l108.6464-15.7696 48.64-98.5088c6.2464-12.6976 18.8416-20.48 32.9728-20.48 14.1312 0 26.7264 7.8848 32.9728 20.48l48.64 98.5088 108.6464 15.7696c13.9264 2.048 25.3952 11.5712 29.696 25.088 4.5056 13.312 0.9216 27.7504-9.216 37.6832z" p-id="2638" fill="#f6ef37"></path></svg>
                       500积分<br><span style="font-size:14px; color:#999">￥500</span>
                       <span v-if="specItem == 'wx'" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                   </div>
                   <div :class="{'specChecked':specItem == 'wx','specItem':true,'ymouse':true}" @click="specItem = 'wx'">
                      <svg t="1594801083672" class="wxicon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2637" width="25" height="25"><path d="M789.8112 234.1888C715.5712 159.9488 616.96 119.0912 512 119.0912s-203.5712 40.8576-277.8112 115.0976S119.0912 407.04 119.0912 512s40.8576 203.5712 115.0976 277.8112S407.04 904.9088 512 904.9088s203.5712-40.8576 277.8112-115.0976S904.9088 616.96 904.9088 512s-40.8576-203.5712-115.0976-277.8112z m-68.1984 242.3808l-78.6432 76.6976L661.504 661.504c2.3552 13.9264-3.1744 27.648-14.6432 35.9424-6.4512 4.7104-14.0288 7.0656-21.6064 7.0656-5.8368 0-11.6736-1.4336-17.1008-4.3008l-97.28-51.0976-97.28 51.0976c-12.4928 6.5536-27.3408 5.5296-38.7072-2.7648-11.3664-8.2944-16.9984-22.1184-14.6432-35.9424L378.88 553.1648l-78.6432-76.6976c-10.1376-9.8304-13.7216-24.2688-9.3184-37.6832 4.4032-13.4144 15.7696-23.04 29.696-24.9856l108.6464-15.7696 48.64-98.5088c6.2464-12.6976 18.8416-20.48 32.9728-20.48 14.1312 0 26.7264 7.8848 32.9728 20.48l48.64 98.5088 108.6464 15.7696c13.9264 2.048 25.3952 11.5712 29.696 25.088 4.5056 13.312 0.9216 27.7504-9.216 37.6832z" p-id="2638" fill="#f6ef37"></path></svg>
                       500积分<br><span style="font-size:14px; color:#999">￥500</span>
                       <span v-if="specItem == 'wx'" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                   </div>
                 
                    </div>
                </div>

                <!-- -------- -->


                 <div class="orderMoney itemBox">
                     <div class="rLeft">订单金额：</div>
                     <div class="rRight ytheamColor" style="font-size:24px;">500元</div>
                 </div>
                 <div class="btnW">
                      <el-button type="primary" class="yprimary">
                          提交订单
                      </el-button>
                 </div>
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
     @import '../../../../../assets/common.scss';
     .recharge{
         .rechargeBox{
             padding:50px 80px 50px;
         }

         
        .specChecked{
             &>span{
                color: $theamColor;
             }
             border: 1px solid $theamColor!important;
         }


          .rechargeTitle{
                font-size:24px;
                font-family:Microsoft YaHei;
                font-weight:bold;
                color:$color1;
                margin-bottom:40px;
          } 

          .itemBox{
                display:flex;
                // border: 1px solid red;
                margin: 20px 0px;
                align-items: center;
                flex-wrap: wrap;

              .rLeft{
                    font-size:14px;
                    font-family:Microsoft YaHei;
                    font-weight:400;
               }

              .rRight{

              }

          }

          

          .rechargeList{
                background:rgba(255,255,255,1);
                // border:1px solid rgba(209,209,209,1);
                border: 1px solid red;
                border-radius:6px;
          }

          .balance{
                font-size:14px;
                font-family:Microsoft YaHei;
                font-weight:400;
                color:$color1;
          }

          .btnW{
              button{
                 font-size:18px;
                 padding:12px 30px;
              }

          }






           .spec{
                    display: flex;
                    align-items: center;


                    .specList{
                       
                    }


                   .specItem{
                       border: 1px solid $underlineColor;
                       margin:10px;
                    //    padding: 2px 15px 10px;
                       position: relative;
                       border-radius: 5px;
                       width: 140px;
                       height:60px;
                       display: inline-block;
                       //overflow: hidden;
                         font-size:16px;
                         font-family:Microsoft YaHei;
                         font-weight:400;
                         text-align: center;

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
</style>
<style lang="scss" scoped>
  
</style>

<style>

</style>