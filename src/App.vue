<script>
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';
import {store} from './store';
import axios from 'axios'

export default{
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data() {
    return {
      store
    }
  },
  created(){
    this.callApi()
  },
  methods: {
    callApi(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res =>{
        const variabile = res.data.data;
        this.store.arrayCardsApi = variabile;
      })
    }
  },
}
</script>


<template>
  <header>
    <HeaderComp/>
  </header>
  <main class="bg-sabbia py-3">
    <MainComp/>
  </main>
</template>


<style>
  
</style>
