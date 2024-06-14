<!-- Qui va la logica del componente (Vue3 + Javascript) -->
<script>
export default {
  name: 'MovieList',
  props: {
    movies: {
      type: Array,
      required: true
    }
  }
};
</script>



<!-- Qui va il contenuto di questo elemento (HTML) -->
<template>
  <div>
    <ul v-if="movies.length">
      <li v-for="movie in movies" :key="movie.id">
        {{ movie.title }}
      </li>
    </ul>
  </div>
</template>



<!-- Qui va lo stile CSS di questo elemento (CSS) -->
<style scoped>
button {
  font-weight: bold;
}
</style>