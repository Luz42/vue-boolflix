<template>
  <section class="border col p-0 d-flex justify-content-center align-items-center position-relative">
    <showPosterComponent :image="movie.poster_path"/>
    <figcaption  class="position-absolute top-50 translate-middle-y w-75">
      <ul>
        <li><strong>Titolo:</strong> {{ movie.title }}</li>
        <li><strong>Titolo originale:</strong> {{ movie.original_title }}</li>
        <li><strong>Lingua originale:</strong> <showFlagComponent :isoFlag="movie.original_language"/> {{ movie.original_language }}</li>
        <li><strong>Voto:</strong><getVoteStarsComponent :vote="movie.vote_average"/></li>
      </ul>
    </figcaption>
  </section>
</template>

<script>
import showFlagComponent from "./showFlagComponent.vue";
import showPosterComponent from "./showPosterComponent.vue";
import getVoteStarsComponent from "./getVoteStarsComponent.vue";


export default {
  name:'moviesListComponent',
  props:{
    movie: Object
  },
  components:{
    showPosterComponent,
    showFlagComponent,
    getVoteStarsComponent
}
}
</script>

<style scoped lang="scss">
  ul{
    list-style: none;
    color: black;
  }
</style>