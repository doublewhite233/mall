<template>
  <div class="goods-info">
    <div v-for="item in subcategoryList" class="goods-info-item">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <div>{{item.title}}</div>
      </a>
    </div>
    <div class="clear"></div>
  </div>
</template>

<script>
  export default {
    name: "CategoryGoodsInfo",
    props: {
      subcategoryList: {
        type: Array,
        default() {
          return []
        }
      }
    }
  }
</script>

<style scoped>
  .goods-info {
    font-size: 14px;
  }

  .goods-info-item {
    width: 80px;
    text-align: center;
    float: left;
  }

  .clear {
    clear: both;
  }

  .goods-info-item img {
    width: 60px;
    margin: 10px 0px 10px 10px;
  }

  .goods-info-item div {
    margin-left: 10px;
  }
</style>
