<template>
  <div class="cart">
<!--    导航-->
    <nav-bar class="nav-bar">
      <div slot="center">购物车({{carLength}})</div>
    </nav-bar>

<!--    列表-->
    <cart-list/>

<!--    底部汇总-->
    <cart-bottom-bar/>
  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";

  import CartList from "./childComps/CartList";
  import CartBottomBar from "./childComps/CartBottomBar";

  import { mapGetters } from 'vuex'

  export default {
    name: "cart",
    components: {
      NavBar,
      CartList,
      CartBottomBar
    },
    computed: {
      // cartLength() {
      //   return this.$store.getters.carLength
      // }
      //两种语法
      ...mapGetters(['carLength'])
      // ...mapGetters({
      //   length: 'carLength'
      // })
    }
  }
</script>

<style scoped>
  .cart {
    height: 100vh;
  }

  .nav-bar {
    background-color: var(--color-tint);
    color: #fff;
    font-weight: bold;
    overflow: hidden;
  }
  .nav-bar:first-child div {
    font-size: 15px;
  }
</style>
