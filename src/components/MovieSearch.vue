<!-- Qui va la logica del componente (Vue3 + Javascript) -->
<script>
export default {
  name: 'MovieSearch',
  data() {
    return {
      query: ''
    };
  },
  methods: {
    search() {
      this.$emit('search-movies', this.query);
    }
  }
};
</script>



<!-- Qui va il contenuto di questo elemento (HTML) -->
<template>
  <div class="search-bar">
    <input v-model="query" @keyup.enter="search" placeholder="Cerca un film..." />

    <!-- Bottone per avviare la ricerca -->
    <button @click="search">
      <img src="../assets/img/search-icon-2048x2048-cmujl7en.png" alt="Search" class="icon">
    </button>
  </div>
</template>



<!-- Qui va lo stile CSS di questo elemento (CSS) -->
<style scoped>
button {
  font-weight: bold;
  border-top-right-radius: 1rem;
  border-bottom-right-radius: 1rem;
  padding: .5rem;
}

input{
  padding: .5rem;
  border-top-left-radius: 1rem;
  border-bottom-left-radius: 1rem;
  border-right-style: none;
  font-size: 16px;
  width: 16rem;
  border-color: black;
}

.search-bar {
  display: flex;
  justify-content: center;
  margin: 20px;
}

.icon{
  width: 1rem;
  margin-left: .2rem;
  margin-right: .4rem;
}
</style>
