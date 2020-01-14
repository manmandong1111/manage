<template>
  <div class="Login-page">
    <div class="container">
      <div class="title">
        <img class="Logo-img" :src="logo">
        <span>小爱<i>ADMIN</i></span>
      </div>
      <el-form class="login-form" ref="ruleForm" :model="loginForm" size="mini" :rules="rules">
        <el-form-item prop="username">
          <span class="iconfont">&#xe610;</span>
          <el-input class="login-input" placeholder="用户名" v-model="loginForm.username"></el-input>
        </el-form-item>
        <el-form-item prop="password">
          <span class="iconfont">&#xe65e;</span>
          <el-input class="login-input" type="password" placeholder="密码" v-model="loginForm.password"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button class="submit-button" type="primary" @click="submitForm('ruleForm')">SIGN IN</el-button>
        </el-form-item>
        <div class="tiparea">
          <p>温馨提示:</p>
          <p class="tip">用户名为：admin/editor(可用于切换权限)</p>
          <p class="tip">密码为：123456</p>
        </div>
      </el-form>
    </div>
  </div>
</template>

<script>
import LogoImg from "../assets/img/logo.png"
export default {
  name: 'Login',
  data () {
    return {
      logo: LogoImg,
      loginForm: {
        username: 'admin',
        password: '123456'
      },
      rules: {
					username: [
            { required: true, message: '请输入用户名', trigger: 'blur' },
            { min: 2, max: 8, message: '长度在 2 到 8 个字符', trigger: 'blur' }
          ],
					password: [
						{ required: true, message: '请输入密码', trigger: 'blur' }
					]
        }
    }
  },
  methods: {
    submitForm (ruleForm) {
      this.$refs[ruleForm].validate( (valid) =>{
        if (valid) {
          this.$message.success("登陆成功")
          this.$router.push('/home')
        }else {
          this.$message.error("请输入账号和密码")
          return false
        }
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
  .Login-page
    position : fixed
    background : url(../assets/img/bg9.jpg) no-repeat center center
    width : 100%
    height : 100%
    background-size : 100% 100%
    .container
      width : 370px
      padding : 25px
      position : absolute
      top : 50%
      left : 50%
      transform :translate(-50%,-50%)
      background : #fff
      border-radius : 5px
      text-align : center
      .title
        width : 100%
        margin-bottom : 20px
        font-size : 22px
        .Logo-img
          width : 40px
          margin-right : 10px
        i
          color: #FF6C60
      .login-form >>> .el-input__inner
        padding-left:30px !important
        height:36px !important 
      .login-form                 
        .submit-button
          width : 100% 
          padding : 13px 0
          font-size: 16px 
          background-color : #FF7C1A
          border-color: #FF7C1A
        .tiparea  
          padding : 10px 0
          font-size : 12px
          text-align : left
          color : #4cbb15 
          .tip
            margin-left : 54px 
        .iconfont
           position : absolute
           top : 50%
           transform : translateY(-50%)
           left : 10px
           z-index : 2
				   font-size : 18px         
</style>
