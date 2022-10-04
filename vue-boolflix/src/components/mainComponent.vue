<template>
  <main class="container-fluid flex-grow-1 d-flex flex-column justify-content-center" style="overflow-y:auto">
      <section class="flex-grow-1" >
        <h4 class="p-3 px-4 m-0">MOVIES</h4>
        <div class="row px-5 pb-3 gap-4 d-flex flex-nowrap" style="overflow-x:auto">
          <moviesListComponent :movie="movie" v-for="movie in movies" :key="movie.id"/>
        </div>
      </section>
      <section class="flex-grow-1">
        <h4 class="p-3 px-4 m-0">SERIES</h4>
        <div class="row px-5 pb-3 gap-4 d-flex flex-nowrap" style="overflow-x:auto">
          <seriesListComponent :serie="serie" v-for="serie in series" :key="serie.id"/>
        </div>
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