<template>
  <main class="container-fluid">
    <div class="row p-5">
      <h2>MOVIES</h2>
      <moviesListComponent :movie="movie" v-for="movie in movies" :key="movie.id"/>
    </div>
    <div class="row p-5">
      <h2>SERIES</h2>
      <seriesListComponent :serie="serie" v-for="serie in series" :key="serie.id"/>
    </div>
  </main>
</template>

<script>
import moviesListComponent from "./moviesListComponent.vue";
import seriesListComponent from "./seriesListComponent.vue";

export default {
    name: "mainComponent",
    props: {
        movies: Array,
        series: Array
    },
    components: {
      moviesListComponent,
      seriesListComponent,
    }
}
</script>

<style scoped lang="scss">

</style>