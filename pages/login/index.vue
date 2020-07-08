<template>
    <div class="login">
              <Header/> 
              <div class="main">
                  <div class="mainImg">
                       <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
                  </div>
                  <div class="mainRight"> 
                       <div class="login-panel">
                           <el-form :model="ruleForm" :rules="rules" ref="ruleForm">
                                <p>
                                    <span :class="{'ymouse':true,'ytheamColor':loginType == 0}"  @click="loginType = 0">密码登录</span>|
                                    <span :class="{'ymouse':true,'ytheamColor':loginType == 1}" @click="loginType = 1">验证码登陆</span>
                                </p>
                                
                                    <el-form-item prop="username">
                                        <el-input placeholder="请输入手机号码或用户名" prefix-icon="el-icon-phone" v-model="ruleForm.username"></el-input>
                                    </el-form-item>
                                    <el-form-item  prop="pwd" v-if="loginType == 0">
                                        <el-input type='password'
                                                placeholder="密码"
                                                prefix-icon="el-icon-unlock"
                                                v-model="ruleForm.pwd">
                                        </el-input>
                                    </el-form-item>


                                    <!-- 验证码登录-->
                                    <el-form-item prop="code" class="verificationCode" v-else>
                                        <el-input 
                                                placeholder="请输入验证码"
                                                v-model="ruleForm.code">
                                        </el-input>
                                        <el-button plain @click="getCode" class="codeBtn">{{codeMsg}}</el-button>
                                    </el-form-item>

                                    
                                  
                                    
                                    
                                    <p>
                                        <span>
                                               <el-checkbox v-model="agreeRule" ></el-checkbox>我已经阅读并同意《<nuxt-link to='/unImportant/userAgreement'>用户协议  </nuxt-link>》
                                        </span>
                                        <nuxt-link to='/unImportant/unLogin'>
                                           无法登陆？
                                        </nuxt-link>
                                    </p>

                                    <el-button @click="submitForm('ruleForm')">登录</el-button>
                                    <p> 
                                         如需开通账户，请点击 <nuxt-link to='/connectService'>联系客服</nuxt-link>
                                    </p>
                           </el-form>
                       </div>
                      
                  </div>
              </div>
              <div class="footer">
              </div>
    </div>
</template>
<script>
// import {login} from '@/util/api.js';
import Header from '@/components/login/header'
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
             codeMsg:'获取验证码', 
             codeMsgNum:0,//倒计时
             returnCode:0,
             agreeRule:false,
           
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
        submitForm(formName) {
        let self = this;
        self.$refs[formName].validate((valid) => {
             console.log("验证---");
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
                   alert("验证码已经发送啦");
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
            console.log("切换登录类型--------")

        }
    },
    components:{
        // vericationCode,
        Header
    }
}
</script>
<style lang="scss" scoped>
   .login{
       width: 1100px;
       margin: auto;
       color: #333333;
   }



   .main{
      display: flex;
      border: 1px solid red;
      .mainImg{
           width: 400px;
           height: 400px;
           margin-top:50px;

           img{
               width: 100%;
               height: 100%;
               border-radius: 30px;
           }
      }

      .mainRight{
          width: 50%;
          border: 2px solid darkblue;
          .login-panel{
              margin: auto;
              margin-top: 30px;
              width: 270px;
              font-size: 14px;
              color:#888888;
              border: 1px solid darkgreen;






          }
      }
   }

</style>
<style lang="scss">
      

</style>
