<template>
    <div class="container-fluid d-flex justify-content-center">
        <div class="container">
            <form><input type="text" id="Artista-box" name="Artista-box"><br></form>
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
/*  data() {},
    methods: {},
    computed: {},
    mounted() {}, */
}
</script>

/* -------------------------------------------------------------------------- */

<style scoped lang="scss">
@import '../assets/scss/variables.scss';
input{
    @include layout-input-1;
}
</style>