<template>
  <div>
  <menu-restaurant-head
      @change-menu="changeMenu"
      class="menu-restaurant__head"/>
<menu-restaurant-main-container
    :names="names"
    class="menus-restaurant__main main-container"/>
  </div>
</template>
<script setup>
import MenuRestaurantHead from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHead";
import MenuRestaurantMainContainer from "@/components/site-body/MainRestaurant/MenuContent/MenuRestaurantMainContainer";
import {ref} from "vue";
let names = ref([])
function changeMenu(n){
  names.value = n;
}
</script>

<style scoped>

</style>