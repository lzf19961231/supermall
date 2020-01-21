<template>
  <tabBar>
    <tabBarItem path="/home" activeColor="deeppink">
      <img slot="item-icon" src="~assets/img/tabBar/home.svg" alt="">
      <img slot="item-icon-active" src="~assets/img/tabBar/home_active.svg" alt="">
      <div slot="item-text">首页</div>
    </tabBarItem>
    <tabBarItem path="/category" activeColor="deeppink">
      <img slot="item-icon" src="~assets/img/tabBar/category.svg" alt="">
      <img slot="item-icon-active" src="~assets/img/tabBar/category_active.svg" alt="">
      <div slot="item-text">分类</div>
    </tabBarItem>
    <tabBarItem path="/cart" activeColor="deeppink">
      <img slot="item-icon" src="~assets/img/tabBar/shopcart.svg" alt="">
      <img slot="item-icon-active" src="~assets/img/tabBar/shopcart_active.svg" alt="">
      <div slot="item-text">购物车</div>
    </tabBarItem>
    <tabBarItem path="/profile" activeColor="deeppink">
      <img slot="item-icon" src="~assets/img/tabBar/profile.svg" alt="">
      <img slot="item-icon-active" src="~assets/img/tabBar/profile_active.svg" alt="">
      <div slot="item-text">我的</div>
    </tabBarItem>
  </tabBar>
</template>

<script>
  import tabBar from 'components/common/tabBar/tabBar';
  import tabBarItem from 'components/common/tabBar/tabBarItem';

    export default {
        name: "mainTabBar",
      components: {
        tabBar,
        tabBarItem
      }
    }
</script>

<style scoped>

</style>
