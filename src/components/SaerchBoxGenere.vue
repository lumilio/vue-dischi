<template>
    <div class="container-fluid d-flex justify-content-center">
        <div class="container">

            <form>
                <label class="text-white">Search for Type :</label>
                <select v-model="selected" @change="showCD(selected)">
                    <option value="All" select>All</option>
                    <option v-for="genere in GeneriArrey" :key='genere.id' :value="genere">{{genere}}</option>
                </select>
            </form>

            
        </div>
    </div>
</template>

/* -------------------------------------------------------------------------- */

<script>
//-----------------utilities--------------------
import 'bootstrap-vue/dist/bootstrap-vue.css';
import 'bootstrap/dist/css/bootstrap.css';
//--------------------------------------------
//---------------components-------------------
// none
//--------------------------------------------



export default {
    name: '',
    components: {},
    props: {},
    data(){
        return {
            CardArreyChild:[],
            GeneriArrey:[],
            selected: 'All',
        };
    },
    methods:{
        generetorGeneriArrey(){
            for (let i = 0; i < this.CardArreyChild.length; i++) {
                const element = this.CardArreyChild[i];
                if(!(this.GeneriArrey.includes(element.genre))){
                    this.GeneriArrey.push(element.genre)
                }
            }
        },
        showCD() {
            this.$emit('filterChange',this.selected);
        },  
    }, 
    mounted(){
        setTimeout(() => {this.CardArreyChild = this.$parent.$data.CardArrey}, 600);
        setTimeout(this.generetorGeneriArrey, 600);
    }
}
</script>

/* -------------------------------------------------------------------------- */

<style scoped lang="scss">
@import '../assets/scss/variables.scss';
select{
    @include layout-input-1;
}
</style>