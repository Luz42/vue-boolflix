<template>
    <header class="container-fluid">
      <div class="row p-2">
        <div class="col text-uppercase"><h1 class="m-0">{{ titleApp }}</h1></div>
        <div class="col d-flex justify-content-end align-items-center">
          <div class="input-group w-50">
            <input 
                  v-model="searchByName"
                  @keyup.enter="findElements()"
                  type="text" 
                  class="form-control" 
                  placeholder="Search Movie/Series" 
                  aria-label="Search Movie/Series" 
                  aria-describedby="button-addon2">
            <button 
                    @click="findElements()"
                    class="btn btn-outline-secondary" 
                    type="button" 
                    id="button-addon2">
                    <font-awesome-icon icon="fa-solid fa-magnifying-glass" />
                  </button>
          </div>
        </div>
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

      props:{
        titleApp: String
      },
        
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
  
  header{
    background-color: black;
    h1{
      color: red;
    }
  }
  </style>