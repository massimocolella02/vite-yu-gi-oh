<template>
    <div class="container bg-white py-4">
        <div class="counter text-white p-2">
            <span>Sono state trovate 20 carte</span>
        </div>
        <div class="cards">
            <SingolaCard/>
        </div>
    </div>
</template>

<script>
import SingolaCard from './SingolaCard.vue'

export default{
    name: 'MainComp',
    components:{
        SingolaCard
    }
}
</script>

<style scoped>
    .counter{
        background-color: #212529;
    }
    .cards{
        display: flex;
        justify-content: space-between;
    }
    .card{
        width: calc(100% / 5 - 10px);
    }
</style>