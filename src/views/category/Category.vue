<template>
  <div class="category">
    <nav-bar class="cate-nav"><div slot="center">分类</div></nav-bar>
    <tab-menu :category-list="categoryList" @itemClick="itemClick"></tab-menu>
    <scroll class="content" ref="scroll">
     <category-goods-info :subcategory-list="subcategoryList"></category-goods-info>
      <tab-control :titles="['综合','新品','销量']" @tabClick="tabClick" class="tab-control"></tab-control>
      <goods-list :goods="showGoods"></goods-list>
    </scroll>
  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";
  import TabMenu from "components/content/tabMenu/TabMenu";
  import Scroll from "components/common/scroll/Scroll";
  import TabControl from "components/content/tabControl/TabControl";
  import GoodsList from "components/content/goods/GoodsList";

  import CategoryGoodsInfo from "./childComps/CategoryGoodsInfo";
  import CategoryGoodsDetail from "./childComps/CategoryGoodsDetail";

  import {getCategory, getSubcategory, getSubcategoryDetail} from "../../network/category";

  export default {
    name: "Category",
    components: {
      NavBar,
      TabMenu,
      Scroll,
      TabControl,
      GoodsList,
      CategoryGoodsInfo,
      CategoryGoodsDetail
    },
    data() {
      return {
        currentIndex: 0,
        categoryList: [],
        subcategoryList: [],
        goods : {
          'pop' : {list: []},
          'new' : {list: []},
          'sell' : {list: []}
        },
        currentType:'new'
      }
    },
    created() {
      this.getCategory()
    },
    methods: {
      itemClick(index){
        this.currentIndex = index
        this.getSubcategory(this.categoryList[this.currentIndex].maitKey)
        this.getSubcategoryDetail('pop')
        this.getSubcategoryDetail('sell')
        this.getSubcategoryDetail('new')
        this.$refs.scroll.refresh()
      },
      tabClick(index){
        switch (index) {
          case 0:
            this.currentType = 'pop';
            break;
          case 1:
            this.currentType = 'new';
            break;
          case 2:
            this.currentType = 'sell';
            break;
        }
      },
      getCategory () {
        getCategory().then(res => {
          this.categoryList = res.data.category.list
          this.getSubcategory(this.categoryList[this.currentIndex].maitKey)
          this.getSubcategoryDetail('pop')
          this.getSubcategoryDetail('sell')
          this.getSubcategoryDetail('new')
        })
      },
      getSubcategory(maitKey) {
        getSubcategory(maitKey).then( res => {
          this.subcategoryList = res.data.list
        })
      },
      getSubcategoryDetail(type) {
        const miniWallkey = this.categoryList[this.currentIndex].miniWallkey;
        getSubcategoryDetail(miniWallkey, type).then(res => {
          this.goods[type].list = res;
        })
      }
    },
    computed: {
      showGoods() {
        return this.goods[this.currentType].list
      }
    }
  }
</script>

<style scoped>
  .category {
    height: 100vh;
    position: relative;
  }

  .cate-nav {
    background-color: var(--color-tint);
    color: #fff;
  }

  .content {
    position: absolute;
    left: 100px;
    top: 44px;
    bottom: 49px;
    overflow: hidden;
  }

  .tab-control {
    margin-top: 10px;
  }
</style>
