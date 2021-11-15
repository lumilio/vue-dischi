<template>
    <div class="container-fluid d-flex justify-content-center">
        <div class="container d-flex justify-content-center">
            <div></div>
            <div></div>
            <CardLayout v-for='Card in CardArrey' v-bind:key="Card.id" 
            :author="Card.author"
            :poster="Card.poster"
            :title="Card.title"
            :year="Card.year"/>
        </div>
    </div>
</template>

/* -------------------------------------------------------------------------- */

<script>
//-----------------utilities--------------------
import 'bootstrap-vue/dist/bootstrap-vue.css';
import 'bootstrap/dist/css/bootstrap.css';
import axios from 'axios';
//--------------------------------------------
//---------------components-------------------
import CardLayout from './Card.vue';
//--------------------------------------------



export default {
    name: 'C2',
    components: {
        CardLayout,
    },
    props: {},
    data() {
        return {
            CardArrey: [],
            error: 'tutto ok',
        };
    },
    created() {
        axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then(myResp => {this.CardArrey = myResp.data.response;})
        .catch(e => {console.error(e, "OPS!"); this.error = 'errore!';})  
        
        console.log(this.CardArrey);
        console.log(this.error);
    },

}
</script>

/* -------------------------------------------------------------------------- */

<style scoped lang="scss">

</style>