<template>
  <section class="border col p-0 d-flex position-relative">
    <showPosterComponent :image="serie.poster_path"/>
    <ul class="position-absolute top-0 left-0">
      <li>titolo: {{ serie.name }}</li>
      <li>titolo originale: {{ serie.original_name }}</li>
      <li>lingua originale: <showFlagComponent :isoFlag="serie.original_language"/> {{ serie.original_language }}</li>
      <li>voto: {{ serie.vote_average }}</li>
      <getVoteStarsComponent :vote="serie.vote_average"/>
    </ul>
  </section>
</template>
  
<script>
import showFlagComponent from "./showFlagComponent.vue";
import showPosterComponent from "./showPosterComponent.vue";
import getVoteStarsComponent from "./getVoteStarsComponent.vue";



export default {
  name:'moviesListComponent',
  props:{
    serie: Object
  },
  components:{
    showPosterComponent,
    showFlagComponent ,
    getVoteStarsComponent
  }
}
</script>

<style scoped lang="scss">

</style>