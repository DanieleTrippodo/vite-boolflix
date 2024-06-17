<template>
  <div class="film-card">
    <img :src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`" alt="Movie Poster" class="MoviePoster"/>  <!-- ho traovato questa CDN che ti permette di gestire le bandierine flagcdn.com -->
    <h3 class="title-movie">{{ movie.title }}</h3>
    <div class="flags flex">
      <img v-for="country in movie.production_countries" :key="country.iso_3166_1" :src="`https://flagcdn.com/w40/${country.iso_3166_1.toLowerCase()}.png`" :alt="country.name" />
    </div>
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

.title-movie{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  width: 10rem;
}

.flags{
  width: 1rem;
  margin-top: .7rem;
}

.flex{
  display: flex;
  gap: .6rem;
}

.MoviePoster{
  width: 10rem;
}

</style>
