<template>
    <div class="container-fluid d-flex justify-content-center">
        <div class="container d-flex align-items-center flex-column">
            <div class="box-form container">
                <BoxSaerchArtista v-on:filterChange='changeFilter'/>
                <BoxSaerchGenere v-on:filterChange='changeFilter'/>
            </div>
            <div v-if='loaded == true' class="Cardbox">                                         <!-- per il tempo di caricamento reale : v-if='CardArrey.length == 10'-->
                <CardLayout v-for='Card in ShowCard' v-bind:key="Card.id" 
                :author="Card.author"
                :poster="Card.poster"
                :title="Card.title"
                :year="Card.year"/>
            </div>
            <div v-else class='loading-box'>
                <h3>Loading...</h3>
            </div>
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
import BoxSaerchArtista from './SaerchBoxArtista.vue';
import BoxSaerchGenere from './SaerchBoxGenere.vue';
//--------------------------------------------



export default {
    name: '',
    components: {
        CardLayout,
        BoxSaerchArtista,
        BoxSaerchGenere,

    },
    props: {},
    data() {
        return {
            CardArrey:[],
            ShowCard:[],
            loaded:false,
        };
    },
    methods:{
        changeFilter(selected) {
            this.ShowCard = [] ;
            for (let i = 0; i < this.CardArrey.length; i++) {
                const element = this.CardArrey[i];
                if(element.author == selected){
                    this.ShowCard.push(element)
                }
                else if(selected == 'All') {
                    this.ShowCard.push(element)
                } 
            }
/*             for (let i = 0; i < this.CardArrey.length; i++) {
                const element = this.CardArrey[i];
                if(element.author == selected){
                    this.ShowCard.push(element)
                }
                else if(selected == 'All') {
                    this.ShowCard.push(element)
                } 
            } */
        }
    },
    mounted() {
        setTimeout(() => { this.loaded = true; }, 700); //---tempo di caricamento finto
        axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then(myResp => {this.CardArrey = myResp.data.response;})
        .catch(e => {console.error(e, 'errore di caricamento');})
    },
}
</script>

/* -------------------------------------------------------------------------- */

<style scoped lang="scss">
@import '../assets/scss/variables.scss';
.Cardbox{
    display: flex;
    margin-top: 10px;
    justify-content: center;
    flex-wrap: wrap;
}
.box-form{
    margin-top: 30px;
}
.loading-box{
    height: 75vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.loading-box h3{
    color: white;
}
</style>