<script setup>
import { ref, computed } from 'vue'

const note1 = ref(0)
const note2 = ref(0)
const note3 = ref(0)

const somme = computed(() => Number(note1.value)+Number(note2.value)+Number(note3.value))
</script>

<template>
    <form action="">
        <input type="number" v-bind:value="note1" @input="event => note1 = event.target.value">
        <input type="number" v-bind:value="note2" @input="event => note2 = event.target.value">
        <input type="number" v-bind:value="note3" @input="event => note3 = event.target.value">

        <p>Somme : {{ somme }}</p>
    </form>
</template>

<style scoped>

</style>