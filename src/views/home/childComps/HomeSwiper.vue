<template>
  <swiper>
    <el-carousel-item v-for="item in banners">
      <a :href="item.link">
        <img :src="item.image" alt="" style="width: 100%;" @load="imageLoad">
      </a>
    </el-carousel-item>
  </swiper>
</template>

<script>
  import Swiper from "components/common/swiper/Swiper";
  import { CarouselItem } from 'element-ui';
  import Vue from "vue";

  Vue.use(CarouselItem);

  export default {
    name: "HomeSwiper",
    data () {
      return {
        isLoad: false
      }
    },
    props: {
      banners:{
        type:Array,
        default() {
          return []
        }
      }
    },
    components:{
      Swiper
    },
    methods: {
      imageLoad() {
        if (!this.isLoad) {
          this.$emit('swiperImageLoad')
          this.isLoad = true
        }
      }
    }
  }
</script>

<style scoped>

</style>