<script setup>
import { ref, reactive } from 'vue'
const variable = 0;
const refVariable = ref(0);
const reactiveVariable = reactive({value: 0});
let myTimer;
function start() {
    myTimer = setInterval(() => {
        refVariable.value++;
        reactiveVariable.value++;
    }, 1000);
}
function stop() {
    clearInterval(myTimer);
}
</script>
<template>
    <span>{{ variable }}</span>
    <br>
    <span>{{ refVariable }}</span>
    <br>
    <span>{{ reactiveVariable.value }}</span>
    <br>
    <button @click="start()">Start</button>
    <br>
    <button @click="stop()">Stop</button>
</template>
<style scoped></style>