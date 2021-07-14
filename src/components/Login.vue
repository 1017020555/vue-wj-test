<template>
  <body id="poster">
    <el-form class="login-container" label-position="left" label-width="0px">

      <h3 class="login_title">系统登录</h3>

      <el-form-item>
          <el-input type="text" v-model="loginForm.username" placeholder="请输入用户名"/>
      </el-form-item>
      <el-form-item>
          <el-input type="password" v-model="loginForm.password" placeholder="请输入密码"/>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" style="width: 100%;background: #505458;border: none" v-on:click="login">登录</el-button>
      </el-form-item>

    </el-form>
  </body>
</template>

<script>
    export default {
        name: 'Login',
        data(){
          return{
            loginForm:{
               username:'',
               password:''
            },
            responseResult: []
          }
        },
        methods:{
            login(){
              this.$axios
                .post('/login',{
                    username:this.loginForm.username,
                    password:this.loginForm.password
                })
                .then(success=>{
                    if (success.data.success == true){
                       this.$router.replace({path:'/index'});
                    }
                })
                .catch(fail=>{

                })
            }
        }
    }
</script>

<style scoped>
  .login-container {
    border-radius: 15px;
    background-clip: padding-box;
    margin: 90px auto;
    width: 350px;
    padding: 35px 35px 15px 35px;
    background: #fff;
    border: 1px solid #eaeaea;
    box-shadow: 0 0 25px #cac6c6;
  }

  .login_title {
    margin: 0px auto 40px auto;
    text-align: center;
    color: #505458;
  }

  #poster {
    background:url("../assets/1.jpg") no-repeat;
    background-position: center;
    height: 100%;
    width: 100%;
    background-size: cover;
    position: fixed;
  }

  body{
    margin: 0px;
  }
</style>
