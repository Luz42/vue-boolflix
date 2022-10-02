<template>
  <section class="border col">
    <ul>
      <li>titolo: {{ movie.title }}</li>
      <li>titolo originale: {{ movie.original_title }}</li>
      <li>lingua originale: <ShowFlagComponent :isoFlag="movie.original_language"/> {{ movie.original_language }}</li>
      <li>voto: {{ movie.vote_average }}</li>
    </ul>
  </section>
</template>

<script>
import ShowFlagComponent from "./showFlagComponent.vue";


export default {
  name:'moviesListComponent',
  props:{
    movie: Object
  },
  components:{
    ShowFlagComponent 
  }
}
</script>

<style scoped lang="scss">

</style>