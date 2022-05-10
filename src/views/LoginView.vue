<template>
  <div class="login">
    <van-nav-bar right-text="先逛一逛">
      <template #left>
        <div id="brand">
          <div class="logo">
            <img src="../assets/icons/home_active.png" alt="" />
          </div>
          <div>Luckin Coffee</div>
        </div>
      </template>
    </van-nav-bar>

    <div id="welcome">欢迎回来</div>
    <div id="welcome_en">Please Login to Your account</div>
    <van-cell-group>
      <van-field
        v-model="val"
        placeholder="请输入用户名"
        @keyup="showVal"
        label="用户名"
      />
      <van-field
        v-bind:type="isVisible ? 'text' : 'password'"
        v-model="password"
        placeholder="请输入密码"
        @keyup="showPass"
        label="密码"
        v-bind:right-icon="isVisible ? 'eye-o' : 'closed-eye'"
        @click-right-icon="switchVisible"
      />
    </van-cell-group>
    <a href="" id="forget">忘记密码?</a>
    <van-button size="large" round class="btn login" color="#0c34ba"
      >登录</van-button
    >
    <van-button size="large" round class="btn register">注册</van-button>
  </div>
</template>


<script>
import "../assets/less/login.less";
export default {
  name: "LoginView",
  data() {
    return {
      val: "",
      password: "",
      isVisible: false,
    };
  },
  methods: {
    showVal() {
      console.log(this.val);
    },
    showPass() {
      console.log(this.password);
    },
    switchVisible() {
      this.isVisible = !this.isVisible;
    },
  },
};
</script>