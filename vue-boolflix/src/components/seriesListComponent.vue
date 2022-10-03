<template>
  <div class="border col p-0 d-flex justify-content-center align-items-center position-relative bg-black">
    <showPosterComponent :image="serie.poster_path"/>
    <figcaption class="p-4 position-absolute">
      <ul class="p-0">
        <li><strong>Titolo: </strong> {{ serie.name }}</li>
        <li><strong>Titolo originale: </strong> {{ serie.original_name }}</li>
        <li><strong>Lingua originale: </strong> <showFlagComponent :isoFlag="serie.original_language"/></li>
        <li><strong>Voto: </strong><getVoteStarsComponent :vote="serie.vote_average"/></li>
        <li v-if="serie.overview"><strong>Overview: </strong>{{serie.overview}}</li>
      </ul>
    </figcaption>
  </div>
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
ul{
    list-style: none;
    *{
      padding: 1% 0;
    }
  }
  figcaption{
    height: 100%;
    width: 100%;
    overflow-y: auto;
    background-color: black;
    z-index: -1;
  }
  div.bg-black:hover figcaption{
    z-index: 1;
  }
</style>