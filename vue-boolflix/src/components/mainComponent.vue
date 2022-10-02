<template>
  <main class="container">
    <div class="row">
      <h2>MOVIES</h2>
      <div class="border col" v-for="movie in movies" :key="movie.id">
        <ul>
          <li>titolo: {{ movie.title }}</li>
          <li>titolo originale: {{ movie.original_title }}</li>
          <li>lingua originale: <ShowFlagComponent :isoFlag="movie.original_language"/> {{ movie.original_language }}</li>
          <li>voto: {{ movie.vote_average }}</li>
        </ul>
      </div>
      <div class="row">
        <h2>SERIES</h2>
        <div class="border col" v-for="serie in series" :key="serie.id">
        <ul>
          <li>titolo: {{ serie.name }}</li>
          <li>titolo originale: {{ serie.original_name }}</li>
          <li>lingua originale: <ShowFlagComponent :isoFlag="serie.original_language"/> {{ serie.original_language }}</li>
          <li>voto: {{ serie.vote_average }}</li>
        </ul>
      </div>
      </div>
    </div>
  </main>
</template>

<script>
import ShowFlagComponent from "./showFlagComponent.vue";

export default {
    name: "mainComponent",
    props: {
        movies: Array,
        series: Array
    },
    components: {
         ShowFlagComponent 
        }
}
</script>

<style scoped lang="scss">

</style>