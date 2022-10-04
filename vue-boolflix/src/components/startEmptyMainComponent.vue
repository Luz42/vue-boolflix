<template>
  <main class="flex-grow-1 d-flex justify-content-center align-items-center">
    <div @click="getStartSearch">
        <font-awesome-icon icon="fa-solid fa-circle-user" style="font-size:10em" />
        <h3 class="p-2 text-center">User</h3>
    </div>
  </main>
</template>

<script>
export default {
    name: 'stertEmptyMainComponent',
    data(){return{
        textToStartSearch: 'a'
    }},

    methods:{
        getStartSearch(){
            this.$emit('startSearch', this.textToStartSearch)
        }
    }
}
</script>

<style lang="scss" scoped>
main{
    background-color: rgb(40, 40, 40);
    color: white;
    div{
        cursor: pointer;
    }
  }
</style>