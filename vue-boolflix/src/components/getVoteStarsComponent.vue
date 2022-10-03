<template>
  <li>{{getVoteMax5}}<font-awesome-icon icon="fa-regular fa-star" />
</li>
</template>

<script>


export default {
    name:'getStarsComponent',
    props:{
        vote: Number
    },
    computed:{
        getVoteMax5(){
            return Math.ceil(parseInt(this.vote) / 2)
            //console.log(fullVote)
        }
    }

}
</script>

<style scoped lang="scss">

</style>