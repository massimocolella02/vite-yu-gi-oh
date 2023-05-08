<template>
    <div class="card">
        <img :src="deattaglicarte.card_images[0].image_url" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ deattaglicarte.name }}</h5>
            <p class="card-text">{{deattaglicarte.archetype}}</p>
        </div>
    </div>
</template>

<script>
    export default{
        name: 'SingolaCard',
        props: ['deattaglicarte']
    }
</script>

<style scoped>
    .card{
        width: calc(100% / 5 - 10px);
        margin-bottom: 10px;
    }
</style>