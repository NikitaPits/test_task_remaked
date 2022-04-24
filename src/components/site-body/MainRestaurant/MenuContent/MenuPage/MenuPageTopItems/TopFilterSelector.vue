<template>
  <div class="selector__list-f">
    <div>
      <h6 v-bind:class="[filterVegetarian?'list-f__one_active':'list-f__one']"
          @click="filterVegetarianClicked()">
        Vegetarian
      </h6>
    </div>
    <div>
      <h6 v-bind:class="[filterContainNuts?'list-f__one_active':'list-f__one']"
          @click="filterContainNutsClicked()">
        Contains Nuts
      </h6>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue";
import {defineEmits} from "vue";

let filterVegetarian = ref(false);
let filterContainNuts = ref(false);
const emits = defineEmits(['vegetarianFilterState','nutsFilterState'])

function filterVegetarianClicked() {
  filterVegetarian.value = !filterVegetarian.value
  emits('vegetarianFilterState', filterVegetarian.value)
}

function filterContainNutsClicked() {
  filterContainNuts.value = !filterContainNuts.value
  emits('nutsFilterState', filterContainNuts.value)
}
</script>

<style scoped>
</style>