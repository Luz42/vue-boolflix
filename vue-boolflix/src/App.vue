<template>
  <div id="app">
    <headerComponent/>
    <mainComponent/>
    <div>
      <input @keyup.enter="showElements()" v-model="searchByName" type="text">
      <button @click="getApi" >search</button>
    </div>
    <div class="row">
      <div class="border col" v-for="movie in movies" :key="movie.id">
        <ul>
          <li>titolo: {{ movie.title }}</li>
          <li>titolo originale: {{ movie.original_title }}</li>
          <li>lingua originale: {{ movie.original_language }}</li>
          <li>voto: {{ movie.vote_average }}</li>
        </ul>
    </div>
    </div>
  </div>
</template>

<script>
import headerComponent from '@/components/headerComponent.vue'
import mainComponent from '@/components/mainComponent.vue'
import axios from 'axios'
import { apiKey } from './env'

export default {
  name: 'App',
  data(){return{
    searchByName:'',
    movies:[],

  }},
  components:{
    headerComponent,
    mainComponent
  },
    // computed:{
    //   showElements(){
    //     this.getApi(this.searchByName)
    //     return this.movies
    //   }
    // },

  //all'avvio della ricerca la stringa che inserirò nell'API assumerà il valore contenuto(v-model)
  methods:{
    //BISOGNA EVITARE DI FARE UNA NUOVA RICHIESTA SE IL VALORE RIMANE INVARIATO
    //
    getApi(){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${this.searchByName}`)
      .then(({data, status})=>{
        if(status === 200){
          this.movies = []
          this.movies.push(...data.results)
          console.log(this.movies)
        }
      })
      .catch(error=> {
        console.log('Errore: ' + error.message)
      })
    }
  }
}
</script>

<style lang="scss">

  @import './assets/main.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
