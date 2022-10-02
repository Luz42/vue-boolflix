<template>
    <header>
    <div>
      <input @keyup.enter="findElements()" type="text" v-model="searchByName">
      <button @click="findElements()" >search</button>
    </div>
    </header>  
</template>
  
  <script>
  export default {
      name: 'headerComponent',
      
      data(){return{
        searchByName: '',
        queryMovies: 'search/movie',
        querySeries: 'search/tv'
      }},
        
      methods:{
        findElements(){

            this.$emit('search', this.searchByName.trim(),this.queryMovies),
            this.$emit('search', this.searchByName.trim(),this.querySeries)
            console.log(this.searchByName.trim())
        }
    }    
  }
  </script>
  
  <style scoped lang="scss">
  
  </style>