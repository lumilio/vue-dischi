<template>
    <div class="card-model">
        <img :src="poster" alt="">
        <h2>{{title}}</h2>
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
</style>