<script>
  import axios from 'axios';

  export default {
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
  <main>
    <input type="text" name="" id="search-input" v-model="inputText">
    <button @click="getFilms(), getSeries()">search</button>
    <ul v-for="movie in movies">
      <li> {{ movie.title }} </li>
      <li> {{ movie.original_title }} </li>
      <li> {{ movie.original_language }} </li>
      <li> {{ movie.vote_average }} </li>
    </ul>
    <ul v-for="serie in series">
      <li> {{ serie.name }} </li>
      <li> {{ serie.original_name }} </li>
      <li> {{ serie.original_language }} </li>
      <li> {{ serie.vote_average }} </li>
    </ul>
  </main>
</template>

<style scoped>

</style>



