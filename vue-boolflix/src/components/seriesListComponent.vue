<template>
  <section class="border col-2 p-3">
    <ul>
      <li>titolo: {{ serie.name }}</li>
      <li>titolo originale: {{ serie.original_name }}</li>
      <li>lingua originale: <showFlagComponent :isoFlag="serie.original_language"/> {{ serie.original_language }}</li>
      <li>voto: {{ serie.vote_average }}</li>
      <showPosterComponent :image="serie.poster_path"/>
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