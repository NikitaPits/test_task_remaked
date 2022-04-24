<template>
  <div>
    <menu-restaurant-head-bg
        :activeChooser="activeChooser"
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
const activeChooser = ref('first')

function changeMenu(n, activeElem) {
  emits('change-menu', n)
  activeChooser.value = activeElem
}
</script>

<style scoped>
</style>