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
                        <span>
                              <el-button type="primary" class="yprimary" size="mini">进入应用</el-button>
                              <el-button type="primary" class="yprimary" size="mini" @click.stop="setting">设置</el-button>
                        </span>
                        <span class="btnW">
                              <el-button type="warning" class="ywarning" size="mini">续费</el-button>
                        </span>
                    </div>
                </div>
            </div>



            <yDilog :title="'应用设置'" ref="dialog" >
                   <div slot='msg' class="dialogList">
                       <div class="listW">
                            <div class="listLeft">
                                <div>应用名称：</div>
                                <div>应用类型：</div>
                                <div>应用简介：</div>
                                <div>应用状态：</div>
                                <div>应用有效期：</div>
                            </div>
                            <div class="listRight">
                                <div class="ymoreTitle1">应用名称</div>
                                <div>应用类型</div>
                                <div>应用简介</div>
                                <div style="color:red">已停用</div>
                                <div>2028-01-02</div>
                            </div>
                        </div>
                        <div class="power">
                              <div class="pTitle">权限设置</div>
                              <div class="pList">
                                  <span> <el-checkbox v-model="checked"></el-checkbox>&nbsp;查询</span>
                                  <span> <el-checkbox v-model="checked"></el-checkbox>&nbsp;发送</span>
                                  <span> <el-checkbox v-model="checked"></el-checkbox>&nbsp;支付</span>
                                  <span> <el-checkbox v-model="checked"></el-checkbox>&nbsp;搜索</span>
                                  <span> <el-checkbox v-model="checked"></el-checkbox>&nbsp;搜索</span>
                                  <span> <el-checkbox v-model="checked"></el-checkbox>&nbsp;搜索</span>
                                  <span> <el-checkbox v-model="checked"></el-checkbox>&nbsp;搜索</span>
                              </div>
                        </div>
                   </div>
                   <span slot="footer" class="dialog-footer">
                        <el-button @click="$refs['dialog'].show = false">取消</el-button>
                        <el-button type="danger" class="ydanger" @click="$refs['dialog'].show = false">停用</el-button>
                    </span>
            </yDilog>


              <yDilog :title="'提示'" ref="tipDialog" >
                   <div slot='msg' class="dialogList">
                        确定要停用这个应用吗？停用后这个应用内的功能无法使用。
                   </div>
                   <span slot="footer" class="dialog-footer">
                        <el-button @click="$refs['tipDialog'].show = false">取消</el-button>
                        <el-button type="danger" class="ydanger" @click="$refs['tipDialog'].show = false">停用</el-button>
                    </span>
            </yDilog>
     </div>
</template>

<script>
import yDilog from '../../../../components/common/yDialog';
export default {
    data(){
        return{
             checked:false

        }
    },
    methods:{
        //跳转到app详情页面
        toAppDetail(){
             console.log("跳转到app详情页面");
             this.$router.push({
                 path:"/app/appDetail"
             })
        },

        setting(){
            console.log(this)
            this.$refs['dialog'].show = true; 
        }
    },
    components:{
        yDilog
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

            .dialogList{
                 //border: 1px solid red;
                  margin-top:-10px;
                  margin-right:30px;
                  .listLeft,.listRight{
                      //border: 1px solid red;
                      margin-right:30px;
                      &>div{
                          margin-bottom: 20px;
                      }
                  }  

                  .listW{
                        // border: 1px solid red;
                        display: flex;
                        border-bottom: 1px solid $underlineColor;
                        .listLeft{
                                font-size:16px;
                                font-family:Microsoft YaHei;
                                color:$color2
                        }

                        .listRight{
                                font-size:16px;
                                font-family:Microsoft YaHei;
                                font-weight:400;
                                color:$color1;

                        }

                  }


                  .power{
                        // border: 1px solid red;

                        .pTitle{
                                font-size:16px;
                                font-family:Microsoft YaHei;
                                font-weight:bold;
                                color:$color1;
                                margin: 10px 0px;
                        }

                        .pList{
                             display: flex;
                             flex-wrap: wrap;

                             span{
                                 margin-right:25px;
                                 font-size: 14px;
                                 color: $color2;
                                 margin-top: 20px;
                             }
                        }

                  }

               
              }
    
</style>

<style lang="scss">
    @import '../../../../assets/common.scss';

    /* 修改checkedbox 的默认样式 */
   .pList{
        .el-checkbox__inner:hover{
            border-color: #999999;
            color: #666;
        }

      .el-checkbox__input.is-checked .el-checkbox__inner, .el-checkbox__input.is-indeterminate .el-checkbox__inner{
           background-color:White;
           border-color: #999999;
           color: #666!important;
           
      }

     
        .el-checkbox__inner::after{
            border-color:$color1;
        }
   }

</style>