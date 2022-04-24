<template>
  <div>
    <menu-page-logotype/>
    <menu-page-top
        v-if="props.activeElem.name"
        @vegetarianFilterState="checkVegetarian"
        @nutsFilterState="checkNuts"
        class="page__top"
        :actualName="props.activeElem.name"
    />
    <menu-box-content
        :activeElem="props.activeElem"
        :filters="filters"
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
const filters = ref([false, false])

function checkVegetarian(vegetarianFilterState) {
  filters.value[0] = vegetarianFilterState
}

function checkNuts(nutsFilterState) {
  filters.value[1] = nutsFilterState
}
</script>

<style scoped>

</style>