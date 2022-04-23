<template>
  <div>
<menu-restaurant-head-bg class="head__bg"/>
  <menu-restaurant-head-title class="head__title"/>
    <menu-restaurant-head-selector
        @change-menu = 'changeMenu'
        class="head__selector"/>
  </div>
</template>

<script setup>
import MenuRestaurantHeadBg from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHeadBg";
import MenuRestaurantHeadTitle from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHeadTitle";
import MenuRestaurantHeadSelector from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHeadSelector";
import {defineEmits} from "vue";
const emits = defineEmits(['change-menu'])

function changeMenu(n){
  emits('change-menu', n)
}
</script>

<style scoped>
</style>