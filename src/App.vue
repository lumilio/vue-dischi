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
/*  props: {},
    data() {},
    methods: {},
    computed: {},
    mounted() {}, */
}
</script>

/* -------------------------------------------------------------------------- */

<style lang="scss">
@import './assets/scss/variables.scss';
#app{
    background-color: $sie-color-1;
    min-height: 100vh;
}
</style>
