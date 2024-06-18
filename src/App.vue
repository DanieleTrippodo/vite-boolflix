<script>
import MovieList from './components/MovieList.vue';

export default {
  components: { MovieList },
};
</script>


<template>
  <div id="app">


    <!-- -Header -- -->
    <header class="flex">

      <div class="marginSmall">
        <img src="./assets/img/BoolFix-18-06-2024.png" alt="Mainlogo" id="logo">
      </div>

      <div class="marginSmall"> <MovieList /> </div>

    </header>
    <!-- -Header -- -->



  </div>
</template>


<style scoped>

header{
  background-color: #30a5a5;
  width: 99.9%;
  padding-top: .5rem;
  padding-bottom: .5rem;

  border-bottom: 1px solid green;
}

.flex{
  display: flex;
  justify-content: space-between;
  align-items: center;
  align-content: center;
  flex-wrap: nowrap;
  flex-direction: row;
}


#logo{
  width: 10rem;
}


.marginSmall{
  margin-left: 1rem;
  margin-right: 1rem;
}
</style>





<!-- # Database che dobbiamo utilizzare 'TheMovieDB' -->
<!-- ----------------------------------------------------------------------- -->
<!-- ? Chiave API:         4ec0ba7c0ea82de7085d2c129e2c544d        -->
<!-- ? API Read Acess Token:    eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI0ZWMwYmE3YzBlYTgyZGU3MDg1ZDJjMTI5ZTJjNTQ0ZCIsInN1YiI6IjY2NmMyOTBjZDVmODljYjE4NzcwZTBhYyIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.lg6q_Yfn43dzUo6jXMwgBykCAcC_aEA6ja0a3Hz4S98                 -->
<!-- ----------------------------------------------------------------------- -->
<!-- todo - Documentazione qui ===>      https://developer.themoviedb.org/reference/intro/getting-started        --> 
<!-- ! IMPORTANTE: quello che ti serve della documentazione lo trovi sulla sezione a destra 'SEARCH' e poi nella sottocategoria 'Movie' -->