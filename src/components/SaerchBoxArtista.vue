<template>
    <div class="container-fluid d-flex justify-content-center">
        <div class="container">

            <form>
                <label class="text-white">Search for Artist :</label>
                <select v-model="selected2" @change="showCD(selected2)">
                    <option value="All" select>All</option>
                    <option v-for="Card in CardArreyChild" :key='Card.id' :value="Card.author" > {{Card.author}}</option>
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
            selected2:'All',
        };
    },
    methods:{
        showCD() {
            this.$emit('filterChange2',this.selected2);
        }
    },  
    mounted(){
        setTimeout(() => {this.CardArreyChild = this.$parent.$data.CardArrey}, 700);
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