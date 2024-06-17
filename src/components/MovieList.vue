<script>
import MovieSearch from './MovieSearch.vue';
import FilmCard from './FilmCard.vue';

export default {
  components: { MovieSearch, FilmCard },
  data() {
    return {
      movies: [],
    };
  },
  methods: {
    setResults(movies) {
      this.movies = movies;
    },
  },
};
</script>


<template>
  <div>
    <MovieSearch @results="setResults" />
    <div v-if="movies.length">
      <FilmCard v-for="movie in movies" :key="movie.id" :movie="movie" />
    </div>
  </div>
</template>



<style scoped>


</style>