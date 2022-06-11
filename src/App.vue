<template>
  <div id="app">
    <HeaderComp/>
    <MainComp :url="apiUrl"/>
    <!-- <CardCompt/> -->
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
// import CardComp from './components/CardComp.vue'
export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    // CardComp
  },
  data(){
    return{
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music'
    }
  }
}
</script>

<style lang="scss">
// @import'~bootstrap/dist/css/bootstrap.css';
@import '~bootstrap/scss/bootstrap';

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
