<template>
<div>
  <main-description class="main__description" />
  <main-panel-menu
      :names="props.names"
      class="panel-menu"/>
</div>
</template>

<script setup>
import MainDescription from "@/components/site-body/MainRestaurant/MenuContent/MainDescription";
import MainPanelMenu from "@/components/site-body/MainRestaurant/MenuContent/MainPanelMenu";
import {defineProps} from "vue";
const props = defineProps({
  names: {
    value: Object,
    required: true
  }
})
</script>

<style scoped>
</style>