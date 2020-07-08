<template>
    <div class="userHead ymouse">
        <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
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
    .userHead{
        border: 1px solid red;
        display: inline-block;
        width: 100px;
        height: 100px;
       

        &:hover{
            &> .list{
                display:block!important;
            }
            
        }
        

        &>img{
             width: 100%;
             height: 100%;
        }

      
        .list{
            background-color:red;
            width: 100%;
            height: 100px;
            position: relative;
            z-index:999;
            display: none;
             transform: translateY(-3px);

            &>div{
                text-align: center;
                
            }
        }
    }
</style>

<style>

</style>