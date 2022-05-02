<template>
  <div>
    <menu-page-logotype/>
    <menu-page-top
        v-if="props.activeElem.name"
        @filters="getFilters"
        class="page__top"
        :actualName="props.activeElem.name"
    />
    <menu-box-content
        :activeElem="props.activeElem"
        :filters="filtersV"
        class="main-box-content"/>

  </div>
</template>

<script setup>
import {defineProps, ref} from "vue";
import MenuPageTop from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageTop";
import MenuPageLogotype from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageLogotype";
import MenuBoxContent from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuBoxContent";

const props = defineProps({
  activeElem: {
    type: Object
  }
})
let filtersV = ref([])

function getFilters(filters){
  filtersV.value=filters;
}


</script>

<style scoped>

</style>