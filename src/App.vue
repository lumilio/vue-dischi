<template>
  <div id="app">
      <HeaderBanner/>
      <CardsContainer/>
  </div>
  
</template>

/* -------------------------------------------------------------------------- */

<script>
//-----------------utilities--------------------
//none
//--------------------------------------------
//---------------components-------------------
import HeaderBanner from './components/Header.vue';
import CardsContainer from './components/Boxcontainer.vue';
//--------------------------------------------



export default {
    name: 'App',
    components: {
        HeaderBanner, 
        CardsContainer,
    },
    props: {},
}
</script>

/* -------------------------------------------------------------------------- */

<style lang="scss">
@import './assets/scss/variables.scss';
#app{
    background-color: $sie-color-1;
    height: 100vh;
}
</style>
