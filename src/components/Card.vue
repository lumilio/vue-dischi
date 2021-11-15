<template>
    <div class="card-model">
        <img :src="poster" alt="">
        <h2>{{title.toUpperCase()}}</h2>
        <span>{{title}}</span>
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
.card-model {
    padding: 0.6rem;
}
.card-model img{
    width: 170px;
    height: 170px;
    object-fit: cover;
    object-position: center top;
}
.card-model p{
    width: 120px;
    margin-top: 8px;
    margin-bottom: 16px;
}
</style>