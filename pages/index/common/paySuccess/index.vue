<template>
    <div class="paySuccess ybox">
         <!-- <img src="../../../../static/img/paySuccess.png" alt=""> -->
         <div class="title">订单支付成功</div>
         <div class="title1">感谢您的支持</div>
    </div>
</template>

<script>
export default {

}
</script>
<style lang="scss" scoped>
@import '../../../../assets/common.scss';
    .paySuccess{
         height: 100%;
         box-sizing: border-box;
         display: flex;
         justify-content: center;
         align-items: center;
         color:$color1;
         flex-direction: column;

         .title{
            font-size:24px;
            font-family:Microsoft YaHei;
            font-weight:bold;
            margin: 10px 0px;

         }
         .title1{
                font-size:16px;
                font-family:Microsoft YaHei;
                font-weight:400;

         }

         img{
            //  border: 1px solid red; 
             width: 130px;
             height: 130px;

         }
         
    }
</style>

<style>

</style>