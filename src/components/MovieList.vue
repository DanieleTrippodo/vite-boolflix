<!-- Qui va la logica del componente (Vue3 + Javascript) -->
<script>
import FilmCard from './FilmCard.vue';

export default {
  name: 'MovieList',
  props: {
    movies: {
      type: Array,
      required: true
    }
  },
  components: {
    FilmCard
  }
};
</script>



<!-- Qui va il contenuto di questo elemento (HTML) -->
<template>
  <div class="movie-list">
    <ul v-if="movies.length">
      <li v-for="movie in movies" :key="movie.id" class="movie-item">
        <FilmCard :movie="movie" />
      </li>
    </ul>
    <div v-else>
      Nessun film trovato.
    </div>
  </div>
</template>



<!-- Qui va lo stile CSS di questo elemento (CSS) -->
<style scoped>
.movie-list {
  margin: 20px;
}

.movie-item {
  margin-bottom: 10px;
}
</style>