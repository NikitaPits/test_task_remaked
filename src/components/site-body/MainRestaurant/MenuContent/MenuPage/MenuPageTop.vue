<template>
  <div>
    <top-title
        :actualName="props.actualName"/>
    <top-filter class="top__filter"/>
  </div>
</template>

<script setup>

import {defineProps} from "vue";
import TopTitle from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTopItems/TopTitle";
import TopFilter from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTopItems/TopFilter";
const props = defineProps({
  actualName:{
    type: String,
    required: true
  }
})

</script>

<style scoped>
</style>