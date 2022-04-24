<template>
  <div>
    <menu-page-logotype/>
    <menu-page-top
        class="page__top"
        :actualName="props.activeElem.name"
    />
    <menu-box-content
        :activeElem="props.activeElem"
        class="main-box-content"/>
  </div>
</template>

<script setup>
import {defineProps} from "vue";
import MenuPageTop from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTop";
import MenuPageLogotype from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageLogotype";
import MenuBoxContent from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuBoxContent";

const props = defineProps({
  activeElem: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>

</style>