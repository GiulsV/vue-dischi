<template>
  <div id="app">
    <HeaderComp :logo="'logo'"/>
    <MainComp/>
    <CardComp/>
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import CardComp from './components/CardComp.vue'
export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    CardComp
  }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  // color: #2c3e50;
  // margin-top: 60px;
}
</style>
