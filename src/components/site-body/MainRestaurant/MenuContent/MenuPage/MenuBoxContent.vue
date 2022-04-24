<template>
  <div>
    <menu-chapter-box
        :activeElem="props.activeElem"
        :filters="props.filters"
    />
  </div>
</template>

<script setup>
import MenuChapterBox from "/src/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuItems/MenuСhapterBox"
import {defineProps} from "vue";

const props = defineProps({
  activeElem: {
    type: Object
  },
  filters:{
    type: Array
  }
})
</script>

<style scoped>

</style>