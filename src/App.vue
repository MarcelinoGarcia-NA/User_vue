<template>
  <div id="app">
    <NavBar/>
    <FooterPage/>
  </div>
</template>
<script>

import FooterPage from './components/Footer.vue';
import NavBar from './components/NavBar.vue';

export default {
  name:'App',
  components:{
    NavBar,
    FooterPage,
  }
}
</script>
<style>
   body{
        left: 0;
        bottom: 0;
        padding: 0;
        margin:0;
   }
</style>
