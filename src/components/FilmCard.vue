<template>
  <div class="film-card">
    <img :src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`" alt="Movie Poster"/>
    <h3>{{ movie.title }}</h3>
  </div>
</template>

<script>
export default {
  props: {
    movie: Object,
  },
};
</script>

<style scoped>
.film-card {
  display: inline-block;
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  text-align: center;
}
.film-card img {
  width: 100%;
  height: auto;
}
</style>
