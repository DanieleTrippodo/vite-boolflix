<!-- Qui va la logica del componente (Vue3 + Javascript) -->
<script>
export default {
  name: 'FilmCard',
  props: {
    movie: {
      type: Object,
      required: true
    }
  }
};
</script>



<!-- Qui va il contenuto di questo elemento (HTML) -->
<template>
  <div class="film-card">
    <h2>{{ movie.title }}</h2>
    <p><strong>Titolo:</strong> {{ movie.original_title }}</p>
    <p><strong>Lingua:</strong> {{ movie.original_language }}</p>
    <p><strong>Voto:</strong> {{ movie.vote_average }}</p>
  </div>
</template>



<!-- Qui va lo stile CSS di questo elemento (CSS) -->
<style scoped>
.film-card {
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}
</style>