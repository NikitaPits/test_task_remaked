<template>
  <div>
    <menu-page-logotype/>
    <menu-page-top
        v-if="props.activeElem.name"
        @filters="filters"
        class="page__top"
        :actualName="props.activeElem.name"
    />
    <menu-box-content
        :activeElem="props.activeElem"
        :filters="filtersObj"
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
let filtersObj = ref({})
function filters(filters){
  filtersObj.value=filters;
}


</script>

<style scoped>

</style>