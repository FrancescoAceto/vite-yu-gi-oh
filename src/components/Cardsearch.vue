<script>
export default {
    name: 'Cardsearch',
    data() {
        return {
            search: ""
        }
    },
}
</script>

<template>
    <div>
        <input v-model="search" type="text" placeholder="Search Cards">
        <button>Search</button>
    </div>
</template>

<style>

</style>