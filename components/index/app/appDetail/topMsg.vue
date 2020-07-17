<template>
    <div class="topMsg">
        <div class="leftImg">
              <div class="ymark ymark1">已采购</div>
              <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
        </div>
        <div class="rightMsg">
              <div class="title ymoreTitle1">
                   应用名称
                  <span class="label">仅认证服务商可开通</span>
              </div>
              <div class="discribe ymoreTitle2">描述信息
                  <span v-for="item in 20" :key="item">就是垃圾弗兰克斯</span>
              </div> 
               <div class="price">
                   <span class="titleName">类型：</span>
                   <span class="titleValue">业务类</span>
              </div>
              <div class="price">
                   <span class="titleName">价格：</span>
                   <span class="titleValue">免费</span>
              </div>
              <div class="spec">
                   <span class="titleName">规格：</span>
                   <div :class="{'specChecked':specItem == 6,'specItem':true,'ymouse':true}" @click="specItem = 6">
                       6个月
                       <span v-if="specItem == 6" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                   </div>
                   <div :class="{'specChecked':specItem == 12,'specItem':true,'ymouse':true}"  @click="specItem = 12">
                       12个月
                        <span v-if="specItem == 12" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                    </div>
                   <div :class="{'specChecked':specItem == 18,'specItem':true,'ymouse':true}" @click="specItem = 18">
                       18个月
                        <span v-if="specItem == 18" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                    </div>
                   <div :class="{'specChecked':specItem == 24,'specItem':true,'ymouse':true}" @click="specItem = 24">
                       24个月
                        <span v-if="specItem == 24" class="iconfont mark icon-xuanzhongjiaobiao"></span>
                    </div>
              </div>
              <div class="buttonW">
                   <el-button @click="confirmOrder" type="danger" style="padding:10px 50px; border-radius:10px;">采购</el-button>
                   <span class="number">已经有888人开通</span>
              </div>
        </div>
    </div>
</template>

<script>
export default {
     data(){
         return{
              specItem:6
         }
     },
     watch:{
         specItem(e){
             console.log(e,"点击切换");
         }
     },
     methods:{
         confirmOrder(){
              console.log("去确认订单页面");

              this.$router.push({
                  path:"/app/confirmOrder"
              })
         }
     }

} 
</script>
<style lang="scss" scoped>
@import '../../../../assets/common.scss';
    $yheight:400px;
    .topMsg{
        //  height:$yheight;
        //  border: 1px solid red;
         display: flex;
         .specChecked{
             color: $theamColor;
             border: 1px solid $theamColor!important;
         }

        .leftImg{
              width:340px;
              height:340px;
              flex-shrink: 0;
              position: relative;
            //   border: 1px solid red;
              overflow: hidden;
              border-radius: 10px;
              overflow: hidden;

              .ymark{
                    position: absolute;
                    width:75%;
                    height:75%;
                    top:-170px;
                    left:-170px;
                    box-sizing: border-box;
                    // background-color:black;
                    transform: rotate(-45deg);
                    // color: white;
                    font-size:18px;

                    display: flex;
                    align-items:flex-end;
                    padding: 3px;
                    justify-content: center;
                }

                            

              img{
                  width: 100%;
                  height: 100%;
                  border-radius: 10px;
              }
        }

        .rightMsg{
            //   border: 1px solid darkblue;
              width: 100%;
              padding: 10px 20px;
              display: flex;
              flex-direction: column;
              justify-content:space-between;

              .titleName{
                    font-size:16px;
                    font-family:Microsoft YaHei;
                    font-weight:400;
                    color:rgba(153,153,153,1);
              }

              .title{
                    font-size:24px;
                    font-family:Microsoft YaHei;
                    font-weight:bold;
                    color:rgba(51,51,51,1);

                    .label{
                        background-color:#E0EEFF;
                        color: #237BE8;
                        font-size: 12px;
                        border-radius: 9px;
                        padding: 2px 8px;
                        margin-left: 10px;
                    }
              }

              .discribe{
                    font-size:16px;
                    font-family:Microsoft YaHei;
                    font-weight:400;
                    color:rgba(51,51,51,1);

              }

              .price{

              }

              .spec{
                    display: flex;
                    align-items: center;
                   .specItem{
                       border: 1px solid $underlineColor;
                       margin:10px;
                       padding: 5px 15px;
                       position: relative;
                       border-radius: 5px;
                       //overflow: hidden;

                       .mark{
                        //    border: 1px solid red;
                           position: absolute;
                           width: 10px;
                           height: 10px;
                           right:19px;
                           bottom:13px;
                           font-size: 30px;
                       }
                   }

              }

              .buttonW{

                  .number{
                        font-size:16px;
                        font-family:Microsoft YaHei;
                        font-weight:400;
                        color:$color2;
                        margin-left: 20px;
                  }

              }










              
         }
    }
</style>

<style>

</style>