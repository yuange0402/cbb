<template>
     <div class="list">
            <div class="listItem ymouse" @click="toAppDetail" v-for="(item,idx) in 10" :key="idx">
                <div class="imgW">
                    <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
                    <div class="mark">升级中</div>
                </div>
                <div class="titleW">
                    <div class="title ymoreTitle1">应用名称决胜巅峰所经历的水电费是</div>
                    <div class="discribe ymoreTitle2">应用描述胜多负少的水电费收到</div>
                    <div class="msg">其他信息胜多负少的水电费</div>
                </div>
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
        //跳转到app详情页面
        toAppDetail(){
             console.log("跳转到app详情页面");
             this.$router.push({
                 path:"/appDetail"
             })
        }

    

    }

}
</script>
<style lang="scss" scoped>

   .list{
       display: flex;
       flex-wrap: wrap;

       .listItem{
            border: 1px solid red;
            display: flex;
            height: 100px;
            margin: 10px;
            width: 300px;
            height: 100px;

            .imgW{
                width: 100px;
                height: 100px;
                flex-shrink:0;
                position: relative;
                overflow: hidden;

                .mark{
                    position: absolute;
                    width:80px;
                    height:80px;
                    top: -40px;
                    right:-40px;
                    background-color:black;
                    transform: rotate(45deg);
                    color: white;

                    display: flex;
                    align-items:flex-end;
                    justify-content: center;
                }
               
                img{
                    width: 100%;
                    height: 100%;
                    position: absolute;
                }
            }

            .titleW{
                padding: 3px 3px 3px 10px;
            }
        }

     }
    
</style>

<style>

</style>