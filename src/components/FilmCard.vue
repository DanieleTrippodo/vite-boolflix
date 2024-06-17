<template>
  <div class="film-card">
    <img :src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`" alt="Movie Poster"/>
    <h3 class="title-movie">{{ movie.title }}</h3>
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
  margin: 1rem;
  padding: 1rem;
  border: 1px solid #00fff2;
  border-radius: 4px;
  text-align: center;
  color: rgb(211, 246, 255);
}
.film-card img {
  width: 10rem;
  height: auto;
}

.title-movie{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  width: 10rem;
}
</style>
