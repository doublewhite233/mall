<template>
  <div class="check-button" :class="{check:isChecked}">
    <img src="~assets/img/cart/tick.svg" alt="">
  </div>
</template>

<script>
  export default {
    name: "CheckButton",
    props: {
      isChecked: {
        type: Boolean,
        default: false
      }
    }
  }
</script>

<style scoped>
  .check-button {
    position: relative;
    height: 20px;
    width: 20px;
    border-radius: 50%;
    border: 2px solid #aaa;
  }
  .check-button img {
    position: absolute;
    top: 2px;
    left: 1px;
    height: 13px;
    width: 13px;
  }

  .check {
    border-color: var(--color-high-text);
    background-color: var(--color-high-text);
  }
</style>