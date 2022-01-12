<template>
  <div id="app">
    <Header @searchDone='search' />
    <Main :moviesList="movies" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from 'axios';

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data: function() {
    return {
      queryValue: '',
      apiKey: 'c6e85928651174bca604719c307a32dc',
      movies: [],
    };
  },
  methods: {
    search: function(userString) {
      this.queryValue = userString;
      this.getMovies();
    },
    getMovies: function() {
      axios.get(
        'https://api.themoviedb.org/3/search/movie', 
        {
          params: {
            api_key: this.apiKey,
            query: this.queryValue,
          }
        }
      ).then((response) => {
        this.movies = response.data.results;
      });
    }
  }
};
</script>

<style lang="scss">
// * {
//   margin: 0;
//   padding: 0;
//   box-sizing: border-box;
// }
</style> 
 