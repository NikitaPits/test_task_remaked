<template>
  <div>
    <h6 class="filter__title">FILTER BY:</h6>
    <top-filter-selector
        v-for="filter in filters"
        :key="filter.id"
        :filter="filter"
        class="filter__selector"
        @picked-filter="pickedFilterId">
      {{ filter.name }}
    </top-filter-selector>
  </div>
</template>

<script setup>

import TopFilterSelector
  from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTopItems/TopFilterSelector";
import jsonFilters from '/src/assets/jsonContent/jsonFilters.json'
import {defineEmits, ref} from "vue";
let filters = ref(jsonFilters)
const emits = defineEmits(['filters'])

function pickedFilterId(state, id) {
  filters.value.forEach(element => {
    if(element.id===id) {
      element.state = state
    }
  })
  emits('filters', filters.value)
}

</script>

<style scoped>
</style>