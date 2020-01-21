<template>
  <div id="home">
    <navBar class="home-nav">
      <div  slot="center">购物街</div>
    </navBar>
  </div>
</template>

<script>
  import navBar from 'components/common/navBar/navBar';
  import {getHomeMultiData} from "network/home";

  export default {
    name: "home",
    components: {
      navBar
    }
  }
</script>

<style scoped>
  .home-nav{
    background-color: var(--color-tint);
    color: #fff;
  }
</style>
