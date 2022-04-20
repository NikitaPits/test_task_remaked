<template>
  <div class="selector__list-f">
<div>
  <h6 v-bind:class="[filterVegetarian?'list-f__one':'list-f__one_active']"
      @click="filterVegetarianClicked()">
    Vegetarian
  </h6>
  </div>
  <div>
  <h6 v-bind:class="[filterContainNuts?'list-f__one':'list-f__one_active']"
      @click="filterContainNutsClicked()">
    Contains Nuts
  </h6>
</div>
  </div>
</template>

<script setup>
import {ref} from "vue";

let filterVegetarian = ref(false);
let filterContainNuts = ref(false);
function filterVegetarianClicked(){
  filterVegetarian.value=!filterVegetarian.value
}
function filterContainNutsClicked(){
  filterContainNuts.value=!filterContainNuts.value
}
</script>

<style scoped>
</style>