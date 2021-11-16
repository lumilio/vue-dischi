<template>
    <div class="container-fluid d-flex justify-content-center">
        <div class="container">

            <form>
                <label for="x">Choose a genere:</label>
                <select name="x" id="x">
                    <option value="volvo">Volvo</option>
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
            theArrey:[]
        };
    },    
    mounted(){
        this.theArrey = this.$parent.$data.CardArrey;
        console.log(this.$parent.$data.CardArrey); 
        console.log(this.theArrey);
    }
}
</script>

/* -------------------------------------------------------------------------- */

<style scoped lang="scss">
@import '../assets/scss/variables.scss';
input{
    @include layout-input-1;
}
</style>