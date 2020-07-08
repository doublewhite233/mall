<template>
  <div class="tab-menu">
    <Scroll class="content">
      <div v-for="(item,index) in categoryList" @click = "itemClick(index)" class="menu-item" :class="{active:index===currentIndex}">{{item.title}}</div>
    </Scroll>
  </div>
</template>

<script>
  import Scroll from "components/common/scroll/Scroll";

  export default {
    name: "TabMenu",
    components: {
      Scroll
    },
    data() {
      return {
        currentIndex: 0
      }
    },
    props: {
      categoryList: {
        type: Array,
        default() {
          return []
        }
      }
    },
    methods: {
      itemClick(index) {
        this.currentIndex = index
        this.$emit('itemClick',index)
      }
    }
  }
</script>

<style scoped>
  .tab-menu {
    background-color: #f6f6f6;
    width: 100px;
    line-height: 50px;
    height: calc(100vh - 93px);
    position: relative;
  }

  .content {
    overflow: hidden;
    position: absolute;
    top: 0px;
    bottom: 0px;
  }

  .menu-item {
    text-align: center;
    width: 100px;
  }

  .active {
    background-color: #fff;
    color: var(--color-high-text);
    border-left: 5px solid var(--color-tint);
  }
</style>
