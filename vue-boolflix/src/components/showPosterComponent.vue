<template>
  <picture>
    <div v-if="!errorImg"><img :src="`https://image.tmdb.org/t/p/w342${image}`" @error="fixImage" alt="#"></div>
    <div v-else><img src="@/assets/imgNotAvailable.png" style="width: 352px; height:513px" alt="#"></div>
  </picture>
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