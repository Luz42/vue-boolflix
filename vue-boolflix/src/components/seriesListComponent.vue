<template>
  <section class="border col">
    <ul>
      <li>titolo: {{ serie.name }}</li>
      <li>titolo originale: {{ serie.original_name }}</li>
      <li>lingua originale: <showFlagComponent :isoFlag="serie.original_language"/> {{ serie.original_language }}</li>
      <li>voto: {{ serie.vote_average }}</li>
      <showPosterComponent :image="serie.poster_path"/>
    </ul>
  </section>
</template>
  
<script>
import showFlagComponent from "./showFlagComponent.vue";
import showPosterComponent from "./showPosterComponent.vue";


export default {
  name:'moviesListComponent',
  props:{
    serie: Object
  },
  components:{
    showPosterComponent,
    showFlagComponent 
  }
}
</script>

<style scoped lang="scss">

</style>