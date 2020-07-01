<template>
  <div class="block">
    <el-carousel :height=nowHeight>
      <slot></slot>
    </el-carousel>
  </div>
</template>

<script>
  import { Carousel } from 'element-ui';
  import Vue from "vue";

  Vue.use(Carousel);


  export default {
    name: "Swiper",
    props: {
      nowHeight: {
        type: String,
        default: '200px'
      }
    }
  }
</script>

<style scoped>

</style>