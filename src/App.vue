<script>
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';
import {store} from './store';
import axios from 'axios';
import SelectComp from "./components/SelectComp.vue";

export default{
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    SelectComp
  },
  data() {
    return {
      store
    }
  },
  created(){
    this.callApi(),
    this.callApiArchetype()
  },
  methods: {
    callApi(){
      if(store.valoreSelect !== ''){
        axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.valoreSelect}`).then(res =>{
          this.store.arrayCardsApi = res.data.data;
        })

      }else{
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then(res =>{
          this.store.arrayCardsApi = res.data.data;
        })
      }
    },

    callApiArchetype(){
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(res =>{
        store.arrayArchetype = res.data;
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
    <SelectComp @ricercaArchetipo="callApi"/>
    <MainComp/>
  </main>
</template>


<style>
  
</style>
