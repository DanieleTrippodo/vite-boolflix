<script setup>
import MovieSearch from './components/MovieSearch.vue'

export default {
  name: 'App',
  components: {
    MovieSearch
  }
/* Contenuto JS e Vue3 */
</script>

<template>
  <!-- Contenuto HTML -->

   <div>
    <MovieSearch @search-movies="fetchMovies" />
   </div>
</template>

<style scoped>
/* Contenuto CSS o SCSS */
</style>











<!-- # Database che dobbiamo utilizzare 'TheMovieDB' -->
<!-- ----------------------------------------------------------------------- -->
<!-- ? Chiave API:         4ec0ba7c0ea82de7085d2c129e2c544d        -->
<!-- ? API Read Acess Token:    eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI0ZWMwYmE3YzBlYTgyZGU3MDg1ZDJjMTI5ZTJjNTQ0ZCIsInN1YiI6IjY2NmMyOTBjZDVmODljYjE4NzcwZTBhYyIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.lg6q_Yfn43dzUo6jXMwgBykCAcC_aEA6ja0a3Hz4S98                 -->
<!-- ----------------------------------------------------------------------- -->
<!-- todo - Documentazione qui ===>      https://developer.themoviedb.org/reference/intro/getting-started        --> 
<!-- ! IMPORTANTE: quello che ti serve della documentazione lo trovi sulla sezione a destra 'SEARCH' e poi nella sottocategoria 'Movie' -->