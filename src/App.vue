<script>
import axios from './axios';
import MovieSearch from './components/MovieSearch.vue';
import MovieList from './components/MovieList.vue';

export default {
  name: 'App',
  components: {
    MovieSearch,
    MovieList
  },
  data() {
    return {
      movies: [],
      loading: false,
      error: null
    };
  },
  methods: {
    async fetchMovies(query) {
      this.loading = true;
      this.error = null;
      try {
        const response = await axios.get('/search/movie', {
          params: {
            api_key: '4ec0ba7c0ea82de7085d2c129e2c544d', // todo - qui dobbiamo sostiturire con la costra API Key
            query,
            language: 'it-IT'
          }
        });
        this.movies = response.data.results;
      } catch (error) {
        this.error = 'Errore nella ricerca dei film';
      } finally {
        this.loading = false;
      }
    }
  }
};
/* Contenuto JS e Vue3 */
</script>








<template>
  <!-- Contenuto HTML -->

  <div class="app">
    <MovieSearch @search-movies="fetchMovies" />
    <div v-if="loading" class="loading">Caricamento...</div>
    <div v-if="error" class="error">{{ error }}</div>
    <MovieList :movies="movies" />
  </div>

</template>











<style scoped>
/* Contenuto CSS o SCSS */



/* #SearchBar{
  display: flex;
  flex-direction: column;       Non serve più per adesso...
  align-items: center;
} */

.app {
  text-align: center;
}

.loading {
  margin: 20px;
  font-size: 18px;
  color: blue;
}

.error {
  margin: 20px;
  font-size: 18px;
  color: red;
}
</style>







<!-- # Database che dobbiamo utilizzare 'TheMovieDB' -->
<!-- ----------------------------------------------------------------------- -->
<!-- ? Chiave API:         4ec0ba7c0ea82de7085d2c129e2c544d        -->
<!-- ? API Read Acess Token:    eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI0ZWMwYmE3YzBlYTgyZGU3MDg1ZDJjMTI5ZTJjNTQ0ZCIsInN1YiI6IjY2NmMyOTBjZDVmODljYjE4NzcwZTBhYyIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.lg6q_Yfn43dzUo6jXMwgBykCAcC_aEA6ja0a3Hz4S98                 -->
<!-- ----------------------------------------------------------------------- -->
<!-- todo - Documentazione qui ===>      https://developer.themoviedb.org/reference/intro/getting-started        --> 
<!-- ! IMPORTANTE: quello che ti serve della documentazione lo trovi sulla sezione a destra 'SEARCH' e poi nella sottocategoria 'Movie' -->