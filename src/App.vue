<template>
  <div>
    <div class="app-head">
      <div class="app-head-inner">
        <router-link :to="{path: '/'}" class="head-logo">
          <img src="./assets/logo.png">
        </router-link>
        <div class="head-nav">
          <ul class="nav-list">
            <li @click="showDialog('isShowLogin')">登录</li>
            <li class="nav-pile">|</li>
            <li @click="showDialog('isShowReg')">注册</li>
            <li class="nav-pile">|</li>
            <li @click="showDialog('isShowAbout')">关于</li>
          </ul>
        </div>
      </div>
    </div>
    <div class="container">
      <keep-alive>
        <router-view></router-view>
      </keep-alive>
    </div>
    <div class="app-foot">
      <p>© 2016 fishenal MIT</p>
    </div>
    <this-dialog :is-show="isShowAbout" @on-close="hideDialog('isShowAbout')">
      <p>本报告在调研数据的基础上，采用定性与定量相结合的方式深入分析了专车市场发展的驱动因素与阻碍因素、专车市场背后的产业格局、专车企业的竞争格局、用户对专车市场的依赖程度、专车对其他交通工具运力的补充效应等，通过这五个章节的研究反映专车市场的发展态势和面临的问题。报告力求客观、深入、准确地反映中国专车市场发展情况，为政府、企事业单位和社会各界提供决策依据。 </p>
    </this-dialog>
    <this-dialog :is-show="isShowLogin" @on-close="hideDialog('isShowLogin')">
      <login-form @on-success="" @on-error=""></login-form>
    </this-dialog>
  </div>
</template>

<script>
import ThisDialog from './components/Dialog'
import LoginForm from './parts/LoginForm'
export default {
  components: {
    ThisDialog,
    LoginForm
  },
  data: function () {
    return {
      isShowAbout: false,
      isShowLogin: false,
      isShowReg: false
    }
  },
  methods: {
    showDialog (param) {
      this[param] = true
    },
    hideDialog (param) {
      this[param] = false
    }
  }
}
</script>

<style>
@import "assets/css/reset.css";
</style>
