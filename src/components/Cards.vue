<script>
    import {store} from "../store.js";
    export default {
        name: 'Cards',
        data() {
            return {
               store,
            }
        },
        props: {
                card: Object,
            },
    }
</script>

<template>
    <div class="cards">
        {{ card.name }} <br>
        {{ card.type }} <br>
    </div>
</template>

<style scoped>
    .cards{
        background-color: rgba(0, 0, 0, 0.5);
        border: 1px solid blue;
        margin-top: 10px;
    }
</style>