<script>
import {store} from "../store.js";
import axios from "axios"; 
import Cards from './Cards.vue';
export default {
  data() {
    return {
      store,
    }
  },
  components: {
  Cards,
},
  created() {
    
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0").then((response) => {
    console.log(response.data.data);
    store.cards = response.data.data;
  });
},
}


</script>

<template>
  <div>
    <h1>Yu-Gi-Oh! First 50 Card-List</h1>
    <Cards v-for="card in store.cards" :card="card"></Cards>
  </div>
</template>

<style>
 h1{
  color: white;
 }
</style>