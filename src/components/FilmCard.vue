<script>
export default {
  props: {
    movie: Object,
  },
  methods: {
    getImageUrl(path, size) {
      const baseUrl = 'https://image.tmdb.org/t/p/';
      return `${baseUrl}${size}${path}`;
    },
  },
};
</script>


<template>
  <div class="film-card">
    <div class="film-card-inner">
      <img :src="getImageUrl(movie.poster_path, 'w342')" alt="Movie Poster"/>
      <div class="film-info">
        <h3 class="Movie-title">{{ movie.title }}</h3>
        <h4>{{ movie.original_title }}</h4>
        <p><strong>Voto:</strong> {{ movie.vote_average }}</p>
      </div>
    </div>
  </div>
</template>


<style scoped>
.film-card {
  position: relative;
  display: inline-block;
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  text-align: center;
  width: 200px;
  overflow: hidden;
}

.film-card-inner {
  position: relative;
}

.film-card img {
  width: 100%;
  height: auto;
  transition: transform 0.3s ease, filter 0.3s ease;
}

.film-card:hover img {
  transform: scale(1.1);
  filter: blur(2px) brightness(70%);
}

.film-info {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
  text-shadow: 0px 0px 10px #30a5a5;
  opacity: 0;
  transition: opacity 0.9s ease;
  text-align: center;
  width: 12rem;
}

.film-card:hover .film-info {
  opacity: 1;
}

.Movie-title{
  margin-bottom: 1rem;
}
</style>
