<template>
    <div class="menu-chapter-box"
         v-for="chapter in props.activeElem.content"
         :key="chapter.id">
      <h4 class="chapter-title"
      >{{chapter.title}}</h4>
      <chapter-dishes :dishes="chapter.dishes"/>
    </div>
</template>

<script setup>
import ChapterDishes from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuItems/ChapterDishes";
import {defineProps} from "vue";
const props = defineProps({
  activeElem:{
    type: Object,
    required: true
  }
})
</script>

<style scoped>

</style>