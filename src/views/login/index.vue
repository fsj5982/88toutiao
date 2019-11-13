<template>
  <div class="login">

    <!-- 卡片组件 -->
    <el-card class="login-card">
      <!-- 卡片内容 -->

      <div class="title">
        <img src="../../assets/img/logo_index.png" alt="">
      </div>
      <el-form style="margin-top:30px">
        <el-form-item>
          <!-- 用户名框 -->
          <el-input></el-input>
        </el-form-item>
        <el-form-item>
          <!-- 验证码框 -->
          <el-input style="width:270px"></el-input>
          <el-button plain style="float:right">获取验证码</el-button>
        </el-form-item>
        <el-form-item>
          <!-- 勾选同意框 -->
          <el-checkbox>我已阅读并同意用户协议及条款</el-checkbox>
        </el-form-item>

        <el-form-item>
          <el-button type="primary" style="width:100%">登录</el-button>
        </el-form-item>
      </el-form>
    </el-card>
  </div>
</template>

<script>
export default {

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
