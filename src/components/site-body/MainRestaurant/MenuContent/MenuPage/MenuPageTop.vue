<template>
  <div>
    <top-title
        v-if="props.actualName"
        :actualName="props.actualName"/>
    <top-filter
        class="top__filter"
        @vegetarianFilterState="checkVegetarian"
        @nutsFilterState="checkNuts"
    />
  </div>
</template>

<script setup>

import {defineProps, defineEmits} from "vue";
import TopTitle from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTopItems/TopTitle";
import TopFilter from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTopItems/TopFilter";

const emits = defineEmits(['vegetarianFilterState','nutsFilterState'])
const props = defineProps({
  actualName: {
    type: String,
    required: true
  }
})

function checkVegetarian(vegetarianFilterState){
  emits('vegetarianFilterState', vegetarianFilterState)
}
function checkNuts(nutsFilterState){
  emits('nutsFilterState', nutsFilterState)
}

</script>

<style scoped>
</style>