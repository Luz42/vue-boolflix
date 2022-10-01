<template>
  <main>
    <div class="row">
      <div class="border col" v-for="movie in items" :key="movie.id">
        <ul>
          <li>titolo: {{ movie.title }}</li>
          <li>titolo originale: {{ movie.original_title }}</li>
          <li>lingua originale: {{ movie.original_language }}</li>
          <li>voto: {{ movie.vote_average }}</li>
        </ul>
      </div>
    </div>
  </main>
</template>

<script>
export default {
    name: 'mainComponent',
    props:{
        items: Array
    }
}
</script>

<style scoped lang="scss">

</style>