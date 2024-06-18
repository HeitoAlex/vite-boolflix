<script>
  import axios from 'axios';
  import AppMainList from './AppMainList.vue';
  import AppSearch from './AppSearch.vue';

  export default {
    components:{
      AppSearch,
      AppMainList
    },

    data(){
      return{
        inputText:'',
        movies: [],
        series: []
      }
    },
    methods:{
      getFilms(){
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=4abd14a4bda72bd354eacef4ac4da057&query='+ this.inputText)

        .then((response) => {
          // handle success
          console.log(response.data.results);
          this.movies = response.data.results

        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        .finally(function () {
          // always executed
        });
      },
      getSeries(){
        axios.get('https://api.themoviedb.org/3/search/tv?api_key=4abd14a4bda72bd354eacef4ac4da057&query=' + this.inputText)

        .then((response) => {
          // handle success
          console.log(response.data.results);
          this.series = response.data.results

        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        .finally(function () {
          // always executed
        });
      }
    },
    created(){
      // this.getFilms();
    }
  }
</script>

<template>
    <header>
        <div id="logo"></div>
        <input type="text" name="" id="search-input" v-model="inputText" @keyup.enter="getFilms(); getSeries()">
    </header>
    <main>
      <AppMainList :movies="movies" :series="series"/>
    </main>
</template>

<style lang="scss" scoped>
  @use '../styles/general.scss' as *;


  header{
    background-color: black;
  }
</style>



