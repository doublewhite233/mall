<template>
  <swiper :nowHeight="nowHeight">
    <el-carousel-item v-for="item in topImages">
      <img :src="item" alt="" style="width: 100%;">
    </el-carousel-item>
  </swiper>
</template>

<script>
  import Swiper from "components/common/swiper/Swiper";
  import { CarouselItem } from 'element-ui';
  import Vue from "vue";

  Vue.use(CarouselItem);

  export default {
    name: "DetailSwiper",
    data() {
      return {
        nowHeight:'300px'
      }
    },
    props: {
      topImages: {
        type: Array,
        default() {
          return []
        }
      }
    },
    components: {
      Swiper
    }
  }
</script>

<style scoped>

</style>