<template>
  <div id="app">
      <HeaderBanner/>

      

  </div>
</template>





<script>


// utilities
import axios from 'axios';
import 'bootstrap-vue/dist/bootstrap-vue.css';
import 'bootstrap/dist/css/bootstrap.css';

// components
import HeaderBanner from './components/Header.vue'


export default {
  name: 'App',
  components: {
      HeaderBanner, 
  },


    data() {
        return {
            cdlist: [],
            error: 'tutto ok',
        };
    },



    mounted() {
        axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then(myResp => {this.cdlist.push(myResp.data.response)}).catch(e => {console.error(e, "OPS!"); this.error = 'errore!';})    
        console.log(this.cdlist);
        console.log(this.error);
    }
}


</script>









<style lang="scss">

    

</style>
