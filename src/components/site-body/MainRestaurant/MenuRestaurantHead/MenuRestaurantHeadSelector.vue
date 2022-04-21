<template>
  <div>
  <div
      class="main-container">
  <div
      v-bind:class="[chosenFirst?'selector__one selector__one-active':'selector__one']"
      v-on:click="chooseSelector1()"
  >
    <h2
        class="head__selector-title">
    West
  </h2>
  </div>
    <div
        v-bind:class="[chosenSecond?'selector__one selector__one-active':'selector__one']"
        v-on:click="chooseSelector2()"
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
  import {defineEmits} from "vue";
  let chosenFirst = ref(true)
  let chosenSecond = ref(false)
  const emits = defineEmits(['change-menu'])
  let names=[
      [
    {name: 'à la carte menu', id: '12sad'},
    {name: 'rose brunch', id: '2'},
    {name: 'cocktails', id: '3'},
    {name: 'desserts', id: '55'},
      ],
      [
        {name: 'Bar menu', id: '1'},
        {name: 'Afternoon tea', id: '2'},
        {name: 'oblix easy', id: '3'},
      ]
  ];
  emits('change-menu', names[0])
  function chooseSelector1(){
    chosenFirst.value = true
    chosenSecond.value = false
    emits('change-menu', names[0])
  }
  function chooseSelector2(){
    chosenFirst.value = false
    chosenSecond.value = true
    emits('change-menu', names[1])
  }
</script>
<style scoped>
</style>