<script>
import {store} from "../store.js";
export default {
    name: 'Cardsearch',
    data() {
        return {
            search: "",
            store,
        }
    },
}
</script>

<template>
    <div>
        <input v-model="search" type="text" placeholder="Search Cards">
        <button @click="$emit('search')">Search</button>
    </div>
</template>

<style>
    input{
        color: blue;
    }
</style>