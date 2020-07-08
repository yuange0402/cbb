<template>
            <!-- 验证码登录-->
             <el-form-item prop="code" class="verificationCode">
                <el-input 
                        placeholder="请输入验证码"
                        v-model="code">
                </el-input>
                <el-button plain @click="getCode" class="codeBtn">{{codeMsg}}</el-button>
             </el-form-item>
</template>

<script>
export default {
    data(){
        return{ 
             codeMsg:'获取验证码', 
             codeMsgNum:0,//倒计时
             returnCode:0,
             code:null,


        }
    },
    props:{
        phone:{
             
        }
    },
    methods:{
        getCode(){
            let that = this;
            let validPhoneN;
            console.log("获取验证码---------------")
           //验证手机号码
        //    this.$refs['ruleForm1'].validateField('phone',(valid,msg) => {
        //        validPhoneN = valid;
        //    })
        //     //验证不通过
        //    if(validPhoneN){ 
        //       console.log("验证不通过")
        //     //验证通过    
        //    }else{
        //         console.log("验证通过")
        //      //判断是不是发送过，并且没有超过30s    
        //        if(this.codeMsgNum == 0){
        //             sendVerifyCode(this.ruleForm1.phone).then(res=>{
        //                 console.log(res,"发送验证码给手机")
        //             })
        //            this.changeCodeMsg();
        //        }else{ 
        //            alert("验证码已经发送啦");
        //        }
        //    }
        },
        changeCodeMsg(){
            let self = this;
            self.codeMsgNum = 60;
            self.codeMsg = '验证码已发送,还有'+self.codeMsgNum+"秒";
            let codeTimeKey = setInterval(()=>{
                console.log("正在定时")
                if(self.codeMsgNum == 0){
                  clearInterval(codeTimeKey);
                  self.codeMsg = '重新发送';
                }else{
                   self.codeMsg = '验证码已发送,还有'+ --self.codeMsgNum +"秒";
                }
            },1000)
        }
    }

}
</script>
<style lang="scss" scoped>
  //  @import '../../assets/common.scss'; 
     .verificationCode{  
          // border: 3px solid $theamColor;
          display:flex!important;
          width: 100%!important;
          justify-content:space-between!important;
          align-items: center!important;

        //   flex-direction: row;

        .el-input { 
            border: 1px solid orange;
            width: 50%;
        }
  

          .codeBtn{
              border: 1px solid orange;
            // background-color:orange;
          } 
     }
</style>