<template>
  <div id="app">

      <div class="bg-dark">fff</div>

  </div>
</template>

<script>

import axios from 'axios';
import 'bootstrap-vue/dist/bootstrap-vue.css';
import 'bootstrap/dist/css/bootstrap.css';




export default {
  name: 'App',
  components: {},

    mounted () {
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => (this.info = response))
  }

}
</script>

<style lang="scss">

</style>
