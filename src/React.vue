<script setup>
import { ref, reactive } from "vue"

const variable = 0
const refVariable = ref(10)
const reactiveVariable = reactive({ data: 20 })

const myTimer = ref(null);
function startTimer() {
  myTimer.value = setInterval(() => {
    refVariable.value += 1;
    reactiveVariable.data += 1;
  }, 1000)
}

function stopTimer() {
  if (myTimer.value) {
    clearInterval(myTimer.value);
    myTimer.value = null;
  }
}










</script>

<template>

  <span>{{ variable }}</span>
  <br>
  <span>{{ refVariable }}</span>
  <br>
  <span>{{ reactiveVariable.data }}</span>
  <br>
  <button @click="startTimer">START</button>
  <br>
  <button @click="stopTimer">STOP</button>
</template>
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
        }, 9);
    }

    function stop() {
        clearInterval(myTimer);
    }



</script>

<template>
    <span>{{ variable }}</span>
    <span>{{ refVariable }}</span>
    <span>{{ reactiveVariable.value }}</span>

    <button @click="start()">Start</button>
    <button @click="stop()">Stop</button>

</template>

<style scoped></style>