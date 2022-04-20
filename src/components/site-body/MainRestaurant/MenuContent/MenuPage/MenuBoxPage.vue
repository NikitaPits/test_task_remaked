<template>
  <div>
    <menu-page-logotype/>
    <menu-page-top
        class="page__top"
        :actualName="props.actualName"
    />
    <div>{{actualName}}</div>
  </div>
</template>

<script setup>
import {defineProps} from "vue";
import MenuPageTop from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTop";
import MenuPageLogotype from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageLogotype";


const props = defineProps({
  actualName:{
    type: String,
    required: true
  }
})
</script>

<style scoped>

</style>