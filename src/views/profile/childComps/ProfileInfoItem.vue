<template>
    <div class="info-item">
      <slot name="item-img"></slot>
      <slot name="item-text"></slot>
    </div>
</template>

<script>
  export default {
    name: "ProfileMine"
  }
</script>

<style scoped>
  .info-item {
    height: 50px;
    width: 100%;
    border-bottom: 2px solid #f2f5f8;
    display: flex;
    line-height: 50px;
  }

  .info-item img {
    height: 30px;
    margin: 10px 20px;
  }
</style>
