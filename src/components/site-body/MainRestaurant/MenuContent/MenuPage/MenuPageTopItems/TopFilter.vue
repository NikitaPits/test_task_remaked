<template>
  <div>
    <h6 class="filter__title">FILTER BY:</h6>
    <top-filter-selector
        @vegetarianFilterState="checkVegetarian"
        @nutsFilterState="checkNuts"
        class="filter__selector"/>
  </div>
</template>

<script setup>

import TopFilterSelector
  from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTopItems/TopFilterSelector";
import {defineEmits} from "vue";

const emits = defineEmits(['vegetarianFilterState','nutsFilterState'])
function checkVegetarian(vegetarianFilterState){
  emits('vegetarianFilterState', vegetarianFilterState)
}
function checkNuts(nutsFilterState){
  emits('nutsFilterState', nutsFilterState)
}
</script>

<style scoped>
</style>