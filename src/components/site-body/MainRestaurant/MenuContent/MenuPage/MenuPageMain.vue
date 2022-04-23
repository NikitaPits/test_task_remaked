<template>
  <div class="menu__box">
<menu-box-page
    v-for="page in pages"
    :key="page.id"
    :activeElem="activeElem"
    v-bind:class="[props.activeElem.name!=page.name?'box__page_disabled':'box__page']"/>
  </div>
</template>

<script setup>
import {defineProps, ref} from "vue";
import MenuBoxPage from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuBoxPage";
import {watch} from "vue";
const props = defineProps({
  activeElem:{
    type: Object
  },
  menus:{
    type: Object
  }
})
const pages = ref()
watch(() => { return props.menus; }, () => {
  pages.value = props.menus;
});

</script>

<style scoped>
</style>