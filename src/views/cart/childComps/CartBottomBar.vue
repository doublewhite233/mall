<template>
  <div class="bottom-bar">
    <div class="check-content">
      <check-button :is-checked="isSelectAll" @click.native="checkClick"></check-button>
      <span>全选</span>
    </div>

    <div class="price">
      合计：{{totalPrice}}
    </div>

    <div class="calculate" @click="calcClick">去计算({{checkLength}})</div>
  </div>
</template>

<script>
  import CheckButton from "components/content/checkButton/CheckButton";

  export default {
    name: "CartBottomVar",
    components: {
      CheckButton
    },
    computed: {
      totalPrice() {
        return '￥' + this.$store.state.cartList.filter(item => {
          return item.checked
        }).reduce((preValue, item) => {
          return preValue + item.price * item.count
        },0).toFixed(2)
      },
      checkLength() {
        return this.$store.state.cartList.filter(item => item.checked).length
      },
      isSelectAll() {
        if (this.$store.state.cartList.length === 0) return false
        return !this.$store.state.cartList.find(item => !item.checked)
      }
    },
    methods: {
      checkClick() {
        if (this.isSelectAll) {
          this.$store.state.cartList.forEach(item => item.checked = false)
        } else {
          this.$store.state.cartList.forEach(item => item.checked = true)
        }
      },
      calcClick() {
        if (this.checkLength===0) {
          this.$toast.show('请选择购买的商品',1500)
        }
      }
    }
  }
</script>

<style scoped>
  .bottom-bar {
    width: 100%;
    height: 50px;
    background-color: #eee;
    position: absolute;
    bottom: 49px;
    line-height: 50px;
    display: flex;
  }

  .check-content {
    display: flex;
    align-items: center;
    margin-left: 10px;
    font-size: 13px;
  }

  .check-content span {
    margin-left: 10px;
    width: 40px;
  }

  .price {
    margin-left: 20px;
    flex: 1;
  }

  .calculate {
    width: 100px;
    background-color: var(--color-high-text);
    color: #fff;
    text-align: center;
  }
</style>