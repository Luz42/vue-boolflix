<template>
  <div id="app" class="d-flex flex-column" style="height:100vh">
    <headerComponent titleApp="boolflix" @search="getApi"/>
    <mainComponent v-if="moviesData.length > 0" :movies="moviesData" :series="seriesData"/>
    <StartEmptyMainComponent @startSearch="getApi" v-else/>
  </div>
</template>

<script>
import headerComponent from '@/components/headerComponent.vue'
import mainComponent from '@/components/mainComponent.vue'
import StartEmptyMainComponent from './components/startEmptyMainComponent.vue'
import axios from 'axios'
import { apiKey } from './env'

export default {
  name: 'App',
  data(){return{
    textSearched:'',
    moviesData:[],
    seriesData:[],
    categories:['search/movie', 'search/tv']

  }},
  components:{
    headerComponent,
    mainComponent,
    StartEmptyMainComponent
},

  //all'avvio della ricerca la stringa che inserirĂ² nell'API assumerĂ  il valore contenuto(v-model)
  methods:{
    //BISOGNA EVITARE DI FARE UNA NUOVA RICHIESTA SE IL VALORE RIMANE INVARIATO
    //*********Come posso fare la chiamata evitando di ripetere il comando?**************** 
    getApi(searchByName){
      if(searchByName !== this.textSearched){
        for(let i = 0; i < this.categories.length; i++){
          axios.get(`https://api.themoviedb.org/3/${this.categories[i]}?api_key=${apiKey}&query=${searchByName}&language=it-IT`)
          .then(({data, status})=>{

          if(status === 200){
            //MOVIES DATA
            if(this.categories[i] === 'search/movie'){
              //console.log(moviesOrSeries)
              this.moviesData = []
              this.moviesData.push(...data.results)
              console.log(this.moviesData)
            //SERIES DATA
            }else{
              //console.log(moviesOrSeries)
              this.seriesData = []
              this.seriesData.push(...data.results)
              console.log(this.seriesData)
            }
            this.textSearched = searchByName
          }
        })
        .catch(error=> {
          console.log('Errore: ' + error.message)
        })
      }
    }}
  }
}
//il figlio invia il dato con la stringa da inserire nella chiamata
//quindi quando la chiamata fatta viene inviata al figlio viene passato anche il dato ricevuto come elemento della funzione
</script>

<style lang="scss">

  @import './assets/main.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}
</style>
