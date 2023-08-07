<template>
  <div id="app">
    <nav-bar></nav-bar>
    <router-view/>
  </div>
</template>

<script>
import navBar from '@/components/navbar.vue'

export default{
  components: {
    navBar
  }
}
</script>

<style lang="scss">

  *{
    padding: 0;
    margin: 0;
  }
</style>
