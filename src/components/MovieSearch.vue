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
  <div>
    <input v-model="query" @keyup.enter="search" placeholder="Cerca un film..." />
    <button @click="search">Cerca</button>
  </div>
</template>



<!-- Qui va lo stile CSS di questo elemento (CSS) -->
<style scoped>
button {
  font-weight: bold;
}
</style>
