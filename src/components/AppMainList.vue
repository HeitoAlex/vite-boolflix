<script>
import SingleMovie from './SingleMovie.vue';
import SingleSerie from './SingleSerie.vue'

export default {
    components:{
        SingleMovie,
        SingleSerie
    },
    data(){
        return{
            
        }
    },   
    props:{
        movies: {
            type: Array,
            required: true
        },
        series: {
            type: Array,
            required: true
        }
    }
}
</script>

<template>
    <div id="movies-list">
        <SingleMovie v-for="movie in movies" :movie="movie"/>
    </div>
    <div id="series-list">
        <SingleSerie v-for="serie in series" :serie="serie"/>
    </div>
</template>

<style scoped>

</style>