<template>
     <div class="connectService">
         <div class="imgW">
             <img src="../../../static/img/connectMe.png" alt="">
         </div>
          <div class="box">
               <div class="title">账号无法登录？请联系客服</div>
               <div class="list">
                    <div class="listItem" v-for="item in connectList" :key="item.title">
                        <div class="left">{{item.title}}</div>
                        <div class="right"><span class="number">{{item.number}}</span>
                            <span class="ymouse" @click="copy('111111111')" @mouseleave="mouseLeave">
                                <el-tooltip class="item" effect="dark" @mouseleave="mouseLeave" :content="copyMsg" placement="right-start">
                                <svg t="1594347730557" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="4243" width="15" height="15"><path d="M931.882 131.882l-103.764-103.764A96 96 0 0 0 760.236 0H416c-53.02 0-96 42.98-96 96v96H160c-53.02 0-96 42.98-96 96v640c0 53.02 42.98 96 96 96h448c53.02 0 96-42.98 96-96v-96h160c53.02 0 96-42.98 96-96V199.764a96 96 0 0 0-28.118-67.882zM596 928H172a12 12 0 0 1-12-12V300a12 12 0 0 1 12-12h148v448c0 53.02 42.98 96 96 96h192v84a12 12 0 0 1-12 12z m256-192H428a12 12 0 0 1-12-12V108a12 12 0 0 1 12-12h212v176c0 26.51 21.49 48 48 48h176v404a12 12 0 0 1-12 12z m12-512h-128V96h19.264c3.182 0 6.234 1.264 8.486 3.514l96.736 96.736a12 12 0 0 1 3.514 8.486V224z" p-id="4244"></path></svg>
                                </el-tooltip>
                            </span>
                        </div>
                    </div>
                </div>
          <div class="btnW">
                 <el-button plain round @click="$router.go(-1)">返回登录</el-button>
          </div>
               
               

          </div>
     </div>
</template>

<script>
export default {
     data(){
         return{
            copyMsg:"复制",
            connectList:[
                {
                    title:"客服电话：",
                    number:"1111"
                },
                {
                    title:"客服微信：",
                    number:"22222"
                },
                {
                    title:"客服qq：",
                    number:"2222222"
                },
                {
                    title:"客服qq群：",
                    number:"1000000"
                },
                {
                    title:"客服邮箱：",
                    number:"788888888"
                },
            ]
         }

     },
     methods:{
              copy(shareLink){
                    var input = document.createElement("input");     // 直接构建input
                    input.value = shareLink;   // 设置内容
                    document.body.appendChild(input);        // 添加临时实例
                    input.select();      // 选择实例内容
                    document.execCommand("Copy");     // 执行复制
                    document.body.removeChild(input);  // 删除临时实例

                    this.copyMsg = "已经复制"
                },

                mouseLeave(){
                     console.log("鼠标离开--")
                     this.copyMsg = "复制"
                },
               
     }

}
</script>
<style lang="scss" scoped>
     .connectService{
        //  border: 5px solid red;
         width: 100%;
        //  height:100vh;
        //  margin:0 0 10vw;
        margin-bottom: 6vw;
         
             img{
                width: 100%;
                height: auto;
             }   


         .box{
            // border: 5px solid red;
            padding:8vmin 0 3vmin;
            width:60%;
            // height:60%;
            margin-left: 20%;
            margin-top:-3%;
            position: relative;
            z-index:99;
            background:rgba(255,255,255,1);
            box-shadow:0px 0px 12px 0px rgba(46,46,46,0.19);
            border-radius:10px;
            display: flex;
            flex-direction: column;
            align-items: center;
            


            .title{
                 font-size: 1.6vw;
                 text-align: center;
            }

            .list{
                //  border: 1px solid red;
                //  text-align:left;
                // transform: translateX(0vw);
                 margin-top:2vw;
                 .listItem{
                     margin: 1.2vw;
                    //  border: 1px solid red;
                     display: flex;
                     justify-content:space-between;
                     color: #999;

                     .number{
                         margin: 0 3vw;
                         color: #333;
                     }
                   

                 }
            }

            .btnW{
                text-align: center;
                // border: 1px solid red;
                margin-top:5vmin;
            }
         }
     }
</style>

<style>

</style>