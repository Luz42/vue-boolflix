<template>
  <main class="container-fluid flex-grow-1 d-flex flex-column" style="overflow-y:auto">
      <section class="row p-5 gap-4 d-flex justify-content-center">
        <h2>MOVIES</h2>
        <moviesListComponent :movie="movie" v-for="movie in movies" :key="movie.id"/>
      </section>
      <section class="row p-5 gap-4 d-flex justify-content-center">
        <h2>SERIES</h2>
        <seriesListComponent :serie="serie" v-for="serie in series" :key="serie.id"/>
      </section>
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
  main{
    background-color: rgb(40, 40, 40);
    color: white;
  }
</style>