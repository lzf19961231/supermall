<template>
  <div id="app">
    <router-view/>
    <mainTabBar/>
  </div>
</template>

<script>
import mainTabBar from 'components/content/mainTabBar/mainTabBar'

export default {
  name: 'app',
  components: {
    mainTabBar
  }
}
</script>

<style>
  @import "assets/css/base.css";
</style>
