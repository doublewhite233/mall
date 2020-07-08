<template>
  <div>
    <nav-bar class="profile-nav"><div slot="center">我的</div></nav-bar>
    <profile-user-info></profile-user-info>
    <profile-info></profile-info>
  </div>
</template>

<script>
  import ProfileUserInfo from "./childComps/ProfileUserInfo";
  import ProfileInfo from "./childComps/ProfileInfo";

  import NavBar from "components/common/navbar/NavBar";

  export default {
    name: "Profile",
    components: {
      ProfileUserInfo,
      ProfileInfo,
      NavBar
    }
  }
</script>

<style scoped>
  .profile-nav {
    background-color: var(--color-tint);
    color: #fff;
  }
</style>
