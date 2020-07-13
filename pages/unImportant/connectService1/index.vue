<template>
     <div class="box">
          <div class="title">账号无法登陆？请联系客服</div>
          <div class="list">
               <div class="listItem">
                   <div class="left">客服电话：</div>
                    <div class="right">111111111
                       <span class="ymouse" @click="copy('111111111')">复制按钮</span>
                    </div>
               </div>
               <div class="listItem">
                   <div class="left" >客服邮箱：</div>
                   <div class="right">111111111
                       <span @click="copy('111111111')" class="ymouse">复制按钮</span>
                   </div>
               </div>
          </div>
          <div class="buttonW">

          </div>
     </div>
</template>

<script>
export default {
     data(){
          return{}
     },
     methods:{
                copy(shareLink){
                    var input = document.createElement("input");     // 直接构建input
                    input.value = shareLink;   // 设置内容
                    document.body.appendChild(input);        // 添加临时实例
                    input.select();      // 选择实例内容
                    document.execCommand("Copy");     // 执行复制
                    document.body.removeChild(input);  // 删除临时实例

                    alert("已经复制到粘贴板")
                }

     }

}
</script>
<style lang="scss" scoped>
    .box{
         border: 1px solid red;

         .title{
             
         }

         .list{
             
         }

         .buttonW{
             
         }
    }
</style>

<style>

</style>