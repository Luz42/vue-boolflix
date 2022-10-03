<template>
    <div>
        <font-awesome-icon 
        v-for="star in STARS_NUMBER" 
        :key="star" 
        :icon="[star <= getVoteMax ? 'fa-solid' : 'fa-regular', 'fa-star']" />
        <!--dovendo assegnare più valori si utilizzano le parentesi quadre-->
    </div>                                                                       
</template>

<script>


export default {
    name:'getStarsComponent',
    data(){return{
        STARS_NUMBER: 5
    }},
    props:{
        vote: Number
    },
    computed:{
        getVoteMax(){
            return Math.ceil(this.vote / 10 * this.STARS_NUMBER)
        }
    }

}
</script>

<style scoped lang="scss">
div{
    display: inline-block;
}
</style>