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
      const apiKey = '4ec0ba7c0ea82de7085d2c129e2c544d';
      const response = await axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${this.query}`);
      this.$emit('results', response.data.results);
    },
  },
};
</script>


<template>
  <div>
    <input v-model="query" @keyup.enter="searchMovie" placeholder="Quale film stai cercando?.."/>
  </div>
</template>


<style scoped>
input{
  margin: 1rem;
}
</style>