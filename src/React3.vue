<script setup>
import { ref, reactive, watch } from 'vue'

const firstName = ref('');
const lastName = ref('');

watch(firstName, (newVal) => {
    console.log('Prenom : ', newVal);
});

watch(lastName, (newVal) => {
    console.log('nom : ', newVal);
});
</script>
<template>
    <form action="">
        <input type="text" v-model="firstName" placeholder="Prénom" />
        <input type="text" v-model="lastName" placeholder="Nom" />
        <button type="submit">Valider</button>
        <h1>Bonjour {{ firstName }} {{ lastName }}</h1>
    </form>
</template>

<style scoped>
</style>