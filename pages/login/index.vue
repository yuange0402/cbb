<template>
    <div class="login">
            <img src="../../static/img/loginBg.png" alt=""> 
            <div class="login-panel">
                <el-form :model="ruleForm" :rules="rules" ref="ruleForm">
                    <p class="header">
                        <span :class="{'ymouse':true,'ytheamColor':loginType == 0}"  @click="loginType = 0">密码登录</span><span class="underlineColor">|</span>
                        <span :class="{'ymouse':true,'ytheamColor':loginType == 1}" @click="loginType = 1">验证码登陆</span>
                    </p>

                    <el-form-item prop="username" class="username">
                        <!-- <el-input class="username" placeholder="请输入手机号码或用户名" prefix-icon="el-icon-phone" v-model="ruleForm.username"></el-input> -->
                        <yInput ref="username" v-model="ruleForm.username" :placeholder="'请输入用户名或手机号'"/>
                    </el-form-item>
                    <el-form-item  prop="pwd" v-if="loginType == 0" class="pwd">
                        <yInput ref="pwd" v-model="ruleForm.pwd" :placeholder="'请输入密码'"/>
                    </el-form-item>


                        <!-- 验证码登录-->
                        <el-form-item prop="code"  v-else>
                            <div class="codeW">
                                 <yInput ref='code' v-model="ruleForm.code" :placeholder="'验证码'" class="code"/>
                                 <!-- <el-button type="primary" plain>主要按钮</el-button> -->
                                 <!-- <div class="codeBtn"></div> -->
                                 <el-button type="primary" size="mini" round plain @click="getCode" :class="{'codeBtn':true,'codeSend':codeMsgNum!=0}">{{codeMsg}}</el-button>
                            </div> 
                        </el-form-item>


                        <el-button type="primary" @click="submitForm('ruleForm')" class="loginBtn">登录</el-button>
                        


                          <p class="userAgreement">
                            <span>
                                <el-checkbox v-model="agreeRule" style="margin-right:10px;"></el-checkbox>我已经阅读并同意《<span class="ymouse ytheamColor" @click="$refs['dialog'].show=true">用户协议</span>》
                            </span>
                            <nuxt-link to='/unImportant/connectService'>
                                无法登陆？
                            </nuxt-link>
                          </p>


                         <div class="errorTip" v-if='errorTip!=""'>
                         <svg t="1594295854029" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3482" width="13" height="13"><path d="M512 0C230.4 0 0 230.4 0 512s230.4 512 512 512 512-230.4 512-512S793.6 0 512 0zM512 877.714286c-40.228571 0-73.142857-32.914286-73.142857-73.142857s32.914286-73.142857 73.142857-73.142857 73.142857 32.914286 73.142857 73.142857S552.228571 877.714286 512 877.714286zM585.142857 512c0 40.228571-32.914286 73.142857-73.142857 73.142857s-73.142857-32.914286-73.142857-73.142857L438.857143 219.428571c0-40.228571 32.914286-73.142857 73.142857-73.142857s73.142857 32.914286 73.142857 73.142857L585.142857 512z" p-id="3483" fill="#d81e06"></path></svg>                             {{errorTip}}</div>
                        <div class="connectService">  
                                如需开通账户，请点击 <nuxt-link to='/unImportant/connectService'>联系客服</nuxt-link>
                        </div>
                </el-form>
            </div>

             <yDialog ref = 'dialog' :title="'用户协议'" :ywidth="'90%'"> 
                   <div slot='msg'>
1111111111111111111
                       <div v-for="item in 100" :key="item">用户协议</div>
                   </div>
                   <span slot="footer" class="dialog-footer">
                        <el-button type="primary" @click="$refs['dialog'].show = false">我知道了</el-button>
                    </span>
             </yDialog>
    </div>
</template>
<script>
// import Header from '@/components/login/header'
import yInput from '@/components/common/yInput';
export default {
    layout:'null',
    data(){

      var checkUsername = (rule, value, callback) => {
        // if (!value) {
        //   return callback(new Error('用户名不能为空！'));
        // }
        // 发送请求验证用户名是不是存在
         console.log(value,"输入的value")
          callback();//代表验证成功


        // setTimeout(() => {
        //   if (!Number.isInteger(value)) {
        //     callback(new Error('请输入数字值'));
        //   } else {
        //     if (value < 18) {
        //       callback(new Error('必须年满18岁'));
        //     } else {
        //       callback();
        //     }
        //   }
        // }, 1000);
      };
        return{
            test:"",
             codeMsg:'获取验证码', 
             codeMsgNum:0,//倒计时
             returnCode:0,
             agreeRule:false,//是不是勾选了条款
             errorTip:"",//底部的错误提示
             
           
            loginType:1,//登录类型 0 密码登录 1 验证码登录
            ruleForm: {
               username:'',
               pwd:'',
               code:""
            },
            rules: {
                username: [
                    { required: true, message: '账户名或手机号不能为空', trigger: 'change' },
                    { validator:checkUsername, trigger: 'change' }
                ],
                pwd: [
                    { required: true, message: '密码不能为空！', trigger: 'change' },
                     { min:6, max:18, message: '密码长度要大于6位！', trigger: 'change' }
                ],
                code:[
                     {required:true,min:4, message: '请输入4位验证码！', trigger: 'change'}
                ],
               
                
            }    
        }
    }, 
    methods: {
        // inputtest(e){
        //     console.log("出发input事件",e,this.test)
        

        // },
        submitForm(formName) {
         let self = this;
         self.$refs[formName].validate((valid) => {
             console.log("验证---",this.ruleForm);
             console.log(valid)
             if(valid){
                //判断当前的是不是同意了条款
                if(this.agreeRule){
                    //判断当前登录类型
                    if(this.loginType == 0){
                        //密码登录
                        console.log("密码登陆")
                    }else{
                        //手机验证码登录
                        console.log("手机验证登陆")
                    }
                    
                }else{
                    //提示同意条款才能继续
                    console.log("没有同意登陆条款")
                
                    this.errorTip = "请勾选同意用户协议"
                }
             }else{
                // 验证不通过
                 console.log("表单验证不通过")

             }
            
       
       
       });
      },





        getCode(){
            let that = this;
            let validPhoneN;
            console.log("获取验证码---------------")
           //验证手机号码
           this.$refs['ruleForm'].validateField('username',(valid,msg) => {
               validPhoneN = valid;
           })
            //验证不通过
           if(validPhoneN){ 
              console.log("验证不通过")
            //验证通过    
           }else{
                console.log("验证通过")
             //判断是不是发送过，并且没有超过30s    
               if(this.codeMsgNum == 0){
                    // sendVerifyCode(this.ruleForm1.phone).then(res=>{
                    //     console.log(res,"发送验证码给手机")
                    // })
                   this.changeCodeMsg();
               }else{ 
                   this.$message("验证码已经发送啦");
               }
           }
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
    },
    watch:{
        // 切换登录类型
        loginType(){
            console.log("切换登录类型--------");
            this.$refs['ruleForm'].clearValidate();

        },
        agreeRule(){
             this.errorTip = ""
        }
    },
    components:{
        // vericationCode,
        // Header,
        // Dialog
        yInput
    }
}


</script>
<style lang="scss" scoped>
   .login{
        //border:5px solid red;
        //background:url('../../static/img/loginBg.png');
        width:100vw;
        height: 100vh;
        min-width: 1200px;
        min-height: 600px;
        position: relative;
        overflow: hidden;
        //height: 100%;
        display: flex;
        align-items: center;


        img{
            position: absolute;
            width: 100%;
            height: 100%;
        }

  


          .login-panel{
              position:absolute;
              right:10%;
              width:304px;
            //   height:482px;
              background:rgba(255,255,255,1);
              box-shadow:0px 0px 24px 0px rgba(46,46,46,0.19);
              border-radius:10px;
              padding:30px 40px 60px;
              

              .header{
                //   border: 1px solid red;
                  display:flex;
                  justify-content: space-around;
                  margin:30px 0px 50px;

              }

              .username,.pwd,.code{
                    // border: 1px solid red;
              }
              
              .codeW{
                //   border: 1px solid red;
                    display: flex;
                //   flex-wrap: ;
                    justify-content: space-between;
                    align-items:center;


                      .code{
                        //    border: 1px solid darkblue;
                            width: 80%;
                            margin-right: 20px;
                        }

                        .codeBtn{
                            flex-shrink: 0;

                        
                        }

                        .codeSend{
                             background:rgba(222,222,222,1);
                            color: #999999;
                            border:none;
                        }

              }

              .userAgreement{
                //    border: 1px solid red;
                   font-size:10px!important;
                   color: #333;

                   display: flex;
                   justify-content: space-between;
                   align-items: center;
                   margin-top: 20px;
              }

              .loginBtn{
                //   border: 1px solid red;
                margin-top:40px;
                width:100%;
                // margin-left: 10%;
              }

              .errorTip{
                   font-size: 13px;
                //    text-align: center;
                    
                   color:#f56c6c;
                   margin-top:20px;
              }

              .connectService{
                   font-size: 13px;
                   text-align: center;
                   color:$color1;
                   margin-top:80px;
              }

          


           }
   }



</style>
<style lang="scss">
  
      

</style>
