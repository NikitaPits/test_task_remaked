<template>
<div>
  <menu-chapter-box
  :activeElem="props.activeElem"/>
</div>
</template>

<script setup>
import MenuChapterBox from "/src/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuItems/MenuСhapterBox"
import {defineProps} from "vue";
const props = defineProps({
  activeElem:{
    type: Object
  }
})
</script>

<style scoped>

</style>