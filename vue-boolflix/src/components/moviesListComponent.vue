<template>
  <section class="border col">
    <ul>
      <li>titolo: {{ movie.title }}</li>
      <li>titolo originale: {{ movie.original_title }}</li>
      <li>lingua originale: <showFlagComponent :isoFlag="movie.original_language"/> {{ movie.original_language }}</li>
      <li>voto: {{ movie.vote_average }}</li>
      <showPosterComponent :image="movie.poster_path"/>
    </ul>
  </section>
</template>

<script>
import showFlagComponent from "./showFlagComponent.vue";
import showPosterComponent from "./showPosterComponent.vue";


export default {
  name:'moviesListComponent',
  props:{
    movie: Object
  },
  components:{
    showPosterComponent,
    showFlagComponent 
  }
}
</script>

<style scoped lang="scss">

</style>