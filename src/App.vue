<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { useCounterStore } from './stores/useCounter'
import { storeToRefs } from 'pinia';

const main = useCounterStore()

const { counter, name } = storeToRefs(main)
const { addOne, reset } = main

// function add(value: number) {
//   main.$patch(state => {
//     state.counter += value
//   })
// }

// function reset() {
//   main.$reset()
// }
</script>

<template>
  <h3>
    <span class="font-extrabold">Counter</span>
    | {{ name }}
  </h3>
  <h4 class="text-9xl my-4">
    {{ counter }} <span class="text-3xl">x 2 = {{ main.doubleCount }}</span>
  </h4>
  <div class="space-x-2">
    <button
      @click="addOne"
      class="border rounded-md shadow-md p-2 bg-green-400 hover:bg-green-500 text-white"
    >Add One</button>
    <button
      @click="reset"
      class="border rounded-md shadow-md p-2 bg-red-400 hover:bg-red-500 text-white"
    >Reset</button>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
