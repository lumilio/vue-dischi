<template>
    <div class="container-fluid d-flex justify-content-center">
        <div class="container">
            <img src="../assets/img/logo.png" alt="">
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
    name: 'C1',
    components: {},
    props: {},
}
</script>

/* -------------------------------------------------------------------------- */

<style scoped lang="scss">
@import '../assets/scss/variables.scss';
.container-fluid{
    background-color: $sie-color-2;
}
img{
    width: 35px;
    margin: 5px;
}
</style>