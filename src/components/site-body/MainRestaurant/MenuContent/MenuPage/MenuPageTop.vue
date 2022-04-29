<template>
  <div>
    <top-title
        v-if="props.actualName"
        :actualName="props.actualName"/>
    <top-filter
        class="top__filter"
        @filters="getFilters"
    />
  </div>
</template>

<script setup>

import {defineProps, defineEmits} from "vue";
import TopTitle from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTopItems/TopTitle";
import TopFilter from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTopItems/TopFilter";

const emits = defineEmits(['filters'])
const props = defineProps({
  actualName: {
    type: String,
    required: true
  }
})

function getFilters(filters){
  emits('filters',filters)
}
</script>

<style scoped>
</style>