<template>
  <div class="block">
    <el-carousel height="200px">
      <slot></slot>
    </el-carousel>
  </div>
</template>

<script>
  import { Carousel } from 'element-ui';
  import Vue from "vue";

  Vue.use(Carousel);


  export default {
    name: "Swiper"
  }
</script>

<style scoped>
</style>