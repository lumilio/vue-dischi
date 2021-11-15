<template>
  <div id="app">

      <div  class="bg-dark">fff</div>

  </div>
</template>





<script>

import axios from 'axios';
import 'bootstrap-vue/dist/bootstrap-vue.css';
import 'bootstrap/dist/css/bootstrap.css';

export default {
  name: 'App',
  components: {},


    data() {
        return {
            cdlist: [],
            error: 'tutto ok',
        };
    },



    mounted() {
        axios
        .get("https://flynn.boolean.careers/exercises/api/random/mail")
        .then(myResp => {this.cdlist.push(myResp.data.response)}).catch(e => {console.error(e, "OPS!"); this.error = 'errore!';})    
        console.log(this.cdlist);
        console.log(this.error);
    }
}


</script>








<style lang="scss">

</style>
