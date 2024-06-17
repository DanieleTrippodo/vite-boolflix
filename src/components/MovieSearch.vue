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
}

img{
  width: 1.5rem;
  padding: .2rem;
}
</style>