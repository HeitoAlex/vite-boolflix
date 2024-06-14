<script>
  import axios from 'axios';

  export default {
    data(){
      return{
        inputText:'',
      }
    },
    methods:{
      getFilms(){
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=4abd14a4bda72bd354eacef4ac4da057&query=$ {inputText}')

        .then((response) => {
          // handle success
          console.log(response);
          
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
    <button @click="getFilms()">search</button>
  </main>
</template>

<style scoped>

</style>



