<script>
import {store} from "../store.js";
import axios from "axios";
import Cardsearch from "./Cardsearch.vue";
import Cards from './Cards.vue';
export default {
  data() {
    return {
      store,
    }
  },
  components: {
  Cards,
  Cardsearch,
},
  created() {
    
    axios.get(this.store.APIsearch).then((response) => {
    console.log(response.data.data);
    this.store.cards = response.data.data;
    store.cards = response.data.data;
  });
},
methods: {
  userSearch(){
    axios.get(this.store.APIsearch).then((response) => {

      if (this.store.cardSearch != "") {
        let Parameter = "&fname=" + this.store.cardSearch;
        axios.get(this.store.APIsearch + Parameter).then((response) =>{
          this.store.cards= response.data.data
        })
      } else{
        axios.get(this.store.APIsearch).then((response) =>{
          this.store.cards= response.data.data
        });
      }
    });
  }
},
}


</script>

<template>
  <div>
    <h1>Yu-Gi-Oh! First 50 Card-List</h1>
    <Cardsearch @search="userSearch()"></Cardsearch>
    <Cards v-for="card in store.cards" :card="card"></Cards>
  </div>
</template>

<style>
 h1{
  color: white;
 }
</style>