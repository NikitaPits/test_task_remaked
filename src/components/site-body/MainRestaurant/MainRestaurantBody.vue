<template>
  <div>
  <menu-restaurant-head
      @change-menu="changeMenu"
      class="menu-restaurant__head"/>
<menu-restaurant-main-container
    :menus="menus"
    class="menus-restaurant__main main-container"/>
  </div>
</template>
<script setup>
import MenuRestaurantHead from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHead";
import MenuRestaurantMainContainer from "@/components/site-body/MainRestaurant/MenuContent/MenuRestaurantMainContainer";
import {ref} from "vue";
let menus = ref([])
function changeMenu(n){
  menus.value = n;
}
</script>

<style scoped>

</style>