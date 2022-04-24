<template>
  <div class="menu__box">
    <menu-box-page
        :activeElem="activeElem"
        class="box__page"/>
  </div>
</template>

<script setup>
import {defineProps, ref} from "vue";
import MenuBoxPage from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuBoxPage";
import {watch} from "vue";

const props = defineProps({
  activeElem: {
    type: Object
  },
  menus: {
    type: Object
  }
})
const pages = ref()
watch(() => {
  return props.menus;
}, () => {
  pages.value = props.menus;
});

</script>

<style scoped>
</style>