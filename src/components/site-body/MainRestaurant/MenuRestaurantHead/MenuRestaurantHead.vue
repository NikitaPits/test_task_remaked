<template>
  <div>
    <menu-restaurant-head-bg
        :currentImage="currentImage"
    />
    <menu-restaurant-head-title class="head__title"/>
    <menu-restaurant-head-selector
        @change-menu='changeMenu'
        class="head__selector"/>
  </div>
</template>

<script setup>
import MenuRestaurantHeadBg from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHeadBg";
import MenuRestaurantHeadTitle from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHeadTitle";
import MenuRestaurantHeadSelector from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHeadSelector";
import {defineEmits, ref} from "vue";

const emits = defineEmits(['change-menu'])
const currentImage = ref('menus-1')

function changeMenu(menuId, menuImage) {
  emits('change-menu', menuId)
  currentImage.value = menuImage
}
</script>

<style scoped>
</style>