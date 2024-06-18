<script>

    export default {
        data(){
            return{
                vote: []
            }
        },
        props:{
            movie:{
                type: Object,
                required:true,
            }
        },
        methods:{
            roundVote(){
                const voto = parseInt(Math.ceil(this.vote_average) / 2, 10);
                console.log(voto) 
            }
        }
    }
</script>

<template>
    <div class="flip-card">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img :src="'https://image.tmdb.org/t/p/w342/' + movie.poster_path" alt="locandina">
            </div>
            <div class="flip-card-back">
                <p>
                    {{ movie.title }}
                </p>
                <p>
                    {{ movie.original_title }}
                </p>
                <p :class="movie.original_language"></p>
                <p>
                    <!-- {{ this.vote }} -->
                </p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss';
    
    
</style>