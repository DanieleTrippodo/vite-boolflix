<script>
import axios from 'axios';

export default {
  data() {
    return {
      query: '',
    };
  },
  methods: {
    async searchMovie() {
      const apiKey = '4ec0ba7c0ea82de7085d2c129e2c544d'; // la mia API di TheMovieDB
      const response = await axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${this.query}`);
      const movieDetails = await Promise.all(response.data.results.map(async (movie) => {
        const details = await axios.get(`https://api.themoviedb.org/3/movie/${movie.id}?api_key=${apiKey}`);
        return details.data;
      }));
      this.$emit('results', movieDetails);
    },
  },
};
</script>


<template>
  <div class="flex">
    <input v-model="query" @keyup.enter="searchMovie" placeholder="Quale film stai cercando?.."/>
    <button @click="searchMovie">   <img src="../assets/img/search-icon-2048x2048-cmujl7en.png" alt="Bottone-Cerca">   </button>
  </div>
</template>


<style scoped>

.flex{
  display: flex;
}

input{
  padding: .5rem;

  border-radius: .8rem;
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
  border-right: none;

  background-color: rgb(63, 62, 62);
  color: white;
}

img{
  width: 1.5rem;
  padding: .2rem;
}

button{
  border-radius: .8rem;
border: none;
  border-top-left-radius: 0;
  border-bottom-left-radius: 0;

  padding: .2rem;

  background-color: rgb(21, 235, 181);
}
</style>