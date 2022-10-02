<template>
  <section class="border col">
            <ul>
            <li>titolo: {{ serie.name }}</li>
            <li>titolo originale: {{ serie.original_name }}</li>
            <li>lingua originale: <ShowFlagComponent :isoFlag="serie.original_language"/> {{ serie.original_language }}</li>
            <li>voto: {{ serie.vote_average }}</li>
            <li>copertina: <img :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" alt="#"></li>
            </ul>
  </section>
</template>
  
<script>
import ShowFlagComponent from "./showFlagComponent.vue";


export default {
  name:'moviesListComponent',
  props:{
    serie: Object
  },
  components:{
    ShowFlagComponent 
  }
}
</script>

<style scoped lang="scss">

</style>