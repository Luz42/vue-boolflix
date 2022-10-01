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
        searchByName: ''
      }},
        
      methods:{
        findElements(){
            this.$emit('search', this.searchByName)
            console.log(this.searchByName)
        }
    }    
  }
  </script>
  
  <style scoped lang="scss">
  
  </style>