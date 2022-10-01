<template>
  <div id="app">
    <headerComponent @search="getApi"/>
    <mainComponent :items="movies"/>
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
    textSearched:'',
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
    //*********Come posso fare la chiamata evitando di ripetere il comando?**************** 
    getApi(searchByName){
      if(searchByName !== this.textSearched){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${searchByName}`)
      .then(({data, status})=>{

        if(status === 200){
          this.movies = []
          this.movies.push(...data.results)
          console.log(this.movies)
          this.textSearched = searchByName
          
        }
      })
      .catch(error=> {
        console.log('Errore: ' + error.message)
      })
    }}
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
