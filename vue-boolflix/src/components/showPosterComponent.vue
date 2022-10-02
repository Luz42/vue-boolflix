<template>
    <li v-if="!errorImg">copertina: <img class="img-fluid" :src="`https://image.tmdb.org/t/p/w342${image}`" @error="fixImage" alt="#"></li>
    <li v-else><img class="img-fluid" src="@/assets/imgNotAvailable.png" alt="#"></li>
</template>

<script>
export default {
  name: 'showPosterComponent',
    
  data(){return{
    errorImg: false
  }},
  props:{
    image: String
  },
  methods:{
    fixImage(){
      this.errorImg = true
      //console.log('error')
    }
  }
}
</script>

<style scoped lang="scss">

</style>