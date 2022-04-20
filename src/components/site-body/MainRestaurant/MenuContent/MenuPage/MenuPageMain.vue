<template>
  <div class="menu__box">
<menu-box-page class="box__page"
    :actualName="props.actualName"/>
  </div>
</template>

<script setup>
import {defineProps} from "vue";
import MenuBoxPage from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuBoxPage";
const props = defineProps({
  actualName:{
    type: String,
    required: true
  }
})
</script>

<style scoped>
</style>