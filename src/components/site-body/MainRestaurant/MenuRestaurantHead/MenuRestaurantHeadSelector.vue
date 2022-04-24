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
import jsonContent from '/src/assets/jsonContent/jsonContent.json'

let chosenFirst = ref(true)
let chosenSecond = ref(false)
const emits = defineEmits(['change-menu'])
emits('change-menu', jsonContent[0])

function chooseSelector1() {
  chosenFirst.value = true
  chosenSecond.value = false
  emits('change-menu', jsonContent[0], 'menus-1')
}

function chooseSelector2() {
  chosenFirst.value = false
  chosenSecond.value = true
  emits('change-menu', jsonContent[1], 'menus-2')
}
</script>
<style scoped>
</style>