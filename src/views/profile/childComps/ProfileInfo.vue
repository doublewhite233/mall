<template>
  <div>
    <div class="main-option">
      <profile-info-item>
        <img src="~assets/img/profile/email.svg" alt="" slot="item-img">
        <div slot="item-text">我的消息</div>
      </profile-info-item>
      <profile-info-item>
        <img src="~assets/img/profile/shop.svg" alt="" slot="item-img">
        <div slot="item-text">积分商城</div>
      </profile-info-item>
      <profile-info-item>
        <img src="~assets/img/profile/card.svg" alt="" slot="item-img">
        <div slot="item-text">会员卡</div>
      </profile-info-item>
    </div>
    <div class="other-option">
      <profile-info-item>
        <img src="~assets/img/tabbar/shopcart_active.svg" alt="" slot="item-img">
        <div slot="item-text">我的购物车</div>
      </profile-info-item>
      <profile-info-item>
        <img src="~assets/img/profile/download.svg" alt="" slot="item-img">
        <div slot="item-text">下载购物APP</div>
      </profile-info-item>
    </div>
  </div>
</template>

<script>
  import ProfileInfoItem from "./ProfileInfoItem";

  export default {
    name: "ProfileInfo",
    components: {
      ProfileInfoItem
    }
  }
</script>

<style scoped>
  .main-option {
    border-bottom: 15px solid #f2f5f8;
  }
</style>
