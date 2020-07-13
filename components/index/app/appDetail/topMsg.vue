<template>
    <div class="topMsg">
        <div class="leftImg">
              <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
        </div>
        <div class="rightMsg">
              <div class="title ymoreTitle1">title</div>
              <div class="discribe ymoreTitle2">描述信息</div>
              <div class="price">价格</div>
              <div class="spec">
                   <div :class="{'specChecked':specItem == 6,'specItem':true,'ymouse':true}" @click="specItem = 6">6个月</div>
                   <div :class="{'specChecked':specItem == 12,'specItem':true,'ymouse':true}"  @click="specItem = 12">12个月</div>
                   <div :class="{'specChecked':specItem == 18,'specItem':true,'ymouse':true}" @click="specItem = 18">18个月</div>
                   <div :class="{'specChecked':specItem == 24,'specItem':true,'ymouse':true}" @click="specItem = 24">24个月</div>
              </div>
              <div class="buttonW">
                   <el-button @click="confirmOrder">续费</el-button>
                   <span>已经有888人开通</span>
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
    $yheight:400px;
    .topMsg{
         height:$yheight;
         border: 1px solid red;
         display: flex;


         .specChecked{
             background-color: orange;
         }

         .leftImg{
              width:$yheight;
              height:$yheight;
              flex-shrink: 0;
              

              img{
                  width: 100%;
                  height: 100%;
              }
         }

         .rightMsg{
              border: 1px solid darkblue;
              width: 100%;


              .title{

              }

              .discribe{

              }

              .price{

              }

              .spec{
                    display: flex;
                   .specItem{
                       border: 1px solid red;
                       margin: 3px;
                       padding: 3px;
                   }

              }

              .buttonW{

              }
         }
    }
</style>

<style>

</style>