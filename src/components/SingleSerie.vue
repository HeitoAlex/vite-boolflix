<script>

    export default {
        data(){
            return{
                vote: []
            }
        },
        props:{
            serie:{
                type: Object,
                required:true
            }
        }
    }
</script>

<template>
    <div class="flip-card">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img :src="'https://image.tmdb.org/t/p/w342/' + serie.poster_path" alt="locandina">
            </div>
            <div class="flip-card-back">
                <p>
                    {{ serie.name }}
                </p>
                <p>
                    {{ serie.original_name }}
                </p>
                <p :class="serie.original_language"></p>
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