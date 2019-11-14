<template>
  <div class="login">

    <!-- 卡片组件 -->
    <el-card class="login-card">
      <!-- 卡片内容 -->

      <div class="title">
        <img src="../../assets/img/logo_index.png" alt="">
      </div>
      <el-form ref="formobj" style="margin-top:30px" :model="loginForm" :rules="loginRules">
        <el-form-item prop="mobile">
          <!-- 用户名框 -->
          <el-input v-model="loginForm.mobile" placeholder="请输入您的手机号"></el-input>
        </el-form-item>
        <el-form-item prop="code">
          <!-- 验证码框 -->
          <el-input style="width:270px" v-model="loginForm.code" placeholder="请输入验证码"></el-input>
          <el-button plain style="float:right">获取验证码</el-button>
        </el-form-item>
        <el-form-item prop="checked">
          <!-- 勾选同意框 -->
          <el-checkbox v-model="loginForm.checked">我已阅读并同意用户协议及条款</el-checkbox>
        </el-form-item>

        <el-form-item>
          <el-button type="primary" style="width:100%" @click="login">登录</el-button>
        </el-form-item>
      </el-form>
    </el-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      loginForm: {
        mobile: '', // 手机号
        code: '', // 验证码
        checked: false // 是否勾选
      },
      loginRules: {
        mobile: [{ required: true, message: '请输入您的手机号' }, {
          pattern: /^1[3456789]\d{9}$/, message: '请输入正确的手机号'
        }], // 手机号
        code: [{ required: true, message: '请输入您的验证码' }, {
          pattern: /^\d{6}$/, message: '请输入正确的验证码'
        }], // 验证码
        checked: [{ validator: function (rule, value, callback) {
          if (value) {
            callback()
          } else {
            callback(new Error('您还没有勾选用户协议'))
          }
        } // 是否勾选
        }]
      }
    }
  },
  methods: {
    login () {
      this.$refs.formobj.validate(function (isok) {
        if (isok) {

        }
      })
    }
  }
}
</script>

<style lang="less" scoped>
.login {
  color: red;
  background: url("../../assets/img/login_bg.jpg");
  height: 100vh;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
  // margin-top: 20px;
  .login-card{
    width: 440px;
    height: 360px;
    .title{
      text-align: center;
      img {
        height: 40px;
      }
    }
  }
}
</style>
