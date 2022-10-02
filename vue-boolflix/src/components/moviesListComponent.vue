<template>
  <section class="border col">
    <ul>
      <li>titolo: {{ movie.title }}</li>
      <li>titolo originale: {{ movie.original_title }}</li>
      <li>lingua originale: <ShowFlagComponent :isoFlag="movie.original_language"/> {{ movie.original_language }}</li>
      <li>voto: {{ movie.vote_average }}</li>
      <li>copertina: <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" @error="showError" alt="#"></li>
    </ul>
  </section>
</template>

<script>
import ShowFlagComponent from "./showFlagComponent.vue";


export default {
  name:'moviesListComponent',
  data(){return{
    errorImg: false
  }},
  props:{
    movie: Object
  },
  components:{
    ShowFlagComponent 
  },
  methods:{
    showError(){
      this.errorImg = true
    }
  }
}
</script>

<style scoped lang="scss">

</style>