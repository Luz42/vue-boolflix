<template>
  <div id="app">
  </div>
</template>

<script>
import axios from 'axios'
import { apiKey } from './env'

export default {
  name: 'App',
  components:{

  },
  // mounted(){
  //   this.getApi()
  // },
  methods:{
    getApi(){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=ritorno+al+futuro`)
      .then((response)=>{
        console.log(response.data)
      })
      .catch(error=> {
        console.log(error)
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
