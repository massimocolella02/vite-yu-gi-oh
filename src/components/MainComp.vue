<template>
    <div class="container bg-white py-4">
        <div class="counter text-white p-2">
            <span>Sono state trovate {{ store.arrayCardsApi.length }} carte</span>
        </div>
        <div class="cards">
            <SingolaCard v-for="(element, index) in store.arrayCardsApi" :key="index" :deattaglicarte="element"/>
        </div>
    </div>
</template>

<script>
import SingolaCard from './SingolaCard.vue'
import { store } from "../store";

export default{
    name: 'MainComp',
    components:{
        SingolaCard
    },
    data() {
        return {
            store
        }
    },
}
</script>

<style scoped>
    .counter{
        background-color: #212529;
    }
    .cards{
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }

</style>