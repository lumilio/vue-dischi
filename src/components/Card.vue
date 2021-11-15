<template>
    <div class="card-model">
        <img :src="poster" alt="">
        <h4>{{title.toUpperCase()}}</h4>
        <span>{{author}}</span>
        <span>{{year}}</span>
    </div>
</template>

/* -------------------------------------------------------------------------- */

<script>
//-----------------utilities--------------------
// none
//--------------------------------------------
//---------------components-------------------
// none
//--------------------------------------------



export default {
    name: 'C2-1',
    components:{},
    props: {
        author: String,
        poster: String,
        title: String,
        year: String,
    }
}
</script>

/* -------------------------------------------------------------------------- */

<style scoped lang="scss">
@import '../assets/scss/variables.scss';

.card-model {
    padding: 0.6rem;
    padding-bottom: 1.3rem;
    background-color: $sie-color-2;
    margin: 10px 5px;
    display: flex;
    align-items: center;
    flex-direction: column;
}
img{
    width: 160px;
    height: 160px;
    object-fit: cover;
    object-position: center top;
}
h4{
    font-size: medium;
    max-width: 140px;
    text-align: center;
    margin-top: 8px;
    margin-bottom: 10px;
    color: white;
}
span{
    font-size: small;
    color: $sie-color-3;
}
</style>