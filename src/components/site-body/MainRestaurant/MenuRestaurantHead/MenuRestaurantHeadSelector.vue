<template>
  <div>
  <div
      class="main-container">
  <div
      v-bind:class="[chosenFirst?'selector__one selector__one-active':'selector__one']"
      v-on:click="chooseSelector1(); $emit('change-menu', names[0])"
  >
    <h2
        class="head__selector-title">
    West
  </h2>
  </div>
    <div
        v-bind:class="[chosenSecond?'selector__one selector__one-active':'selector__one']"
        v-on:click="chooseSelector2(); $emit('change-menu', names[1])"
    >
  <h2
      class="head__selector-title">
    East
  </h2>
    </div>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue"
let chosenFirst = ref(true)
let chosenSecond = ref(false)
let names=[
    [
  {name: 'à la carte menu', id: '1'},
  {name: 'rose brunch', id: '2'},
  {name: 'cocktails', id: '3'},
  {name: 'desserts', id: '4'},
    ],
    [
      {name: 'Bar menu', id: '1'},
      {name: 'Afternoon tea', id: '2'},
      {name: 'oblix easy', id: '3'},
    ]
];

function chooseSelector1(){
  chosenFirst.value = true
  chosenSecond.value = false
}
function chooseSelector2(){
  chosenFirst.value = false
  chosenSecond.value = true
}
</script>
<style scoped>
</style>