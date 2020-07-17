<template>
     <div class="list">
            <div class="listItem ymouse" @click="toAppDetail" v-for="(item,idx) in 20" :key="idx">
                <div class="imgW">
                    <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
                    <div class="ymark ymark1">已采购</div>
                    <!-- <div class="mark mark2">升级中</div> -->
                    <!-- <div class="mark mark3">已过期</div> -->
                </div>
                <div class="titleW">
                    <div class="title ymoreTitle1">
                        应用名称
                        <span class="label">仅认证服务商可开通</span>
                    </div>
                    <div class="discribe ymoreTitle2">应用描述胜多负就是了九分裤洛杉矶的弗兰克圣诞节快乐圣诞节里看风景扣篮大赛所经历的就了开发商讲道理少的水电费收到</div>
                    <div class="msg">
                        <span class="number">188亿人开通</span>
                        <span class="btnW">
                              <el-button type="danger" class="ydanger" size="mini">免费</el-button>
                              <el-button type="danger" class="ydanger" size="mini">免费</el-button>
                        </span>
                    </div>
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
                 path:"/app/appDetail"
             })
        }
    }
}
</script>
<style lang="scss" scoped>
@import '../../../../assets/common.scss';
   .list{
       display: flex;
       flex-wrap: wrap;
       .listItem{
            border: 1px solid #eee;
            border-radius: 10px;
            display: flex;
            // height: 100px;
            margin: 10px;
            width:462px;
            // height:144px;
            padding: 18px;

            .imgW{
                width: 108px;
                height: 108px;
                border-radius: 10px;
                flex-shrink:0;
                position: relative;
                overflow: hidden;

                .ymark{
                    position: absolute;
                    width:75%;
                    height:75%;
                    top: -40px;
                    left:-40px;
                    box-sizing: border-box;
                    // background-color:black;
                    transform: rotate(-45deg);
                    // color: white;
                    font-size: 13px;

                    display: flex;
                    align-items:flex-end;
                    padding: 3px;
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
                // border: 1px solid red;
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                width: 100%;

                .title{
                    font-size: 18px;
                    font-family:Microsoft YaHei;
                    font-weight:bold;
                    color:#333333;
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
                      font-size: 14px;
                 }

                 .msg{
                      display: flex;
                      justify-content: space-between;
                      align-items: flex-end;
                      .number{
                           color: $color2;
                           font-size: 14px;                  
                       }

                       .btnW{
                        //    border: 1px solid darkorange;
                       }
                 }



            }
        }

     }
    
</style>

<style>

</style>