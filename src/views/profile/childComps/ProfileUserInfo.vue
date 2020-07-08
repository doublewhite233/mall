<template>
    <div>
      <div class="info">
        <img src="~assets/img/profile/avatar.svg" alt="" id="info-avatar">
        <span class="login">登录/注册</span>
        <img src="~assets/img/profile/mobile.svg" alt="" class="info-mobile">
        <span class="info-mobile">暂无绑定手机号</span>
      </div>
      <div class="account">
        <div class="account-detail">
          <div><span>0.00</span>元</div>
          <div>我的余额</div>
        </div>
        <div class="account-detail">
          <div><span>0</span>个</div>
          <div>我的优惠</div>
        </div>
        <div class="account-detail">
          <div><span>0</span>分</div>
          <div>我的积分</div>
        </div>
      </div>
    </div>
</template>

<script>
  export default {
    name: "ProfileUserInfo"
  }
</script>

<style scoped>
  .info {
    background-color: var(--color-tint);
    color: #fff;
    padding: 15px 20px;
    font-size: 20px;
    position: relative;
  }

  #info-avatar {
    width: 80px;
    margin: 5px 20px 5px 10px;
  }

  .login {
    position: absolute;
    margin-top: 25px;
  }

  .info-mobile {
    height: 14px;
    font-size: 15px;
    position: relative;
    top: -10px;
  }

  .account {
    display: flex;
    text-align: center;
    border-bottom: 15px solid #f2f5f8;
  }

  .account-detail {
    flex: 1;
    border-left: 1px solid rgba(0,0,0,.1);
    padding: 20px 10px;
    font-size: 15px;
  }

  .account-detail span {
    font-size: 26px;
    color: var(--color-high-text);
  }
</style>
