<template>
    <div class="container-fluid d-flex justify-content-center">
        <div class="container">

            <form>
                <label for="x">Choose a car:</label>
                <select name="x" id="x">
                    <option v-for="Card in CardArreyChild" :key='Card.id' value="Card.author">{{Card.author}}</option>
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
            CardArreyChild:[]
        };
    },   
    mounted(){
        setTimeout(() => {this.CardArreyChild = this.$parent.$data.CardArrey}, 700);
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