<template>
  <div>
    <menu-restaurant-head-bg
        :currentImage="props.currentImage"
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
import {defineEmits,defineProps} from "vue";
const props = defineProps({
  currentImage:{
    type: String
  }
})
const emits = defineEmits(['change-menu'])


function changeMenu(menuId) {
  emits('change-menu', menuId)
}
</script>

<style scoped>
</style>