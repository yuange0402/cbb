<template>
    <div class="userHead ymouse">
        <div class="imgW">
            <img src="../../static/img/loginBg.png">  
        </div>
        <div class="list">
             <div>
                 <nuxt-link to='/accountCenter'>账户管理</nuxt-link>
             </div>
             <div @click="exit">退出登录</div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{

        }
    },
    methods:{
        exit(){
             console.log("退出登录")
            //发送请求退出登录，

            // 跳转路由到登录页面
            this.$router.push({
                path:"/login"
            })
        }
    }

}
</script>
<style lang="scss" scoped>
@import '../../assets/common.scss'; 
    .userHead{
        // border: 1px solid red;
        // display: inline-block;
        width: 100px;
        height: 100%;
        border-radius: 10px;
        margin-top:1px;
        


       

        &:hover{
            &> .list{
                display:block!important;
                 background-color:#999999;
            }
            background-color:#999999;
            
        }

        .imgW{
            width:$headerHeight;
            height:$headerHeight;
           
            margin: auto;
            left: 0;
            right: 0;
            display: flex;
            justify-content: center;
            align-items: center;
           

            &>img{
                width:35px;
                height:35px;
                  border-radius: 5px;
            }
        }
        


      
        .list{
            // background-color:red;
            width: 100%;
            height: 100px;
            position: relative;
            z-index:999;
            display: none;
             transform: translateY(-3px);
             padding-top: 20px;
             border-radius: 0px 0px 10px 10px;
             margin-top: -5px;

            &>div{
                text-align: center;
                
            }
        }
    }
</style>

<style>

</style>