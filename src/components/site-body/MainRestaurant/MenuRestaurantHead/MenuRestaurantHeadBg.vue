<template>
  <div class="head__bg"
       :style="computedStyle">
  </div>
</template>

<script setup>
import {computed, defineProps} from "vue";

const props = defineProps({
  currentImage: {
    type: String
  }
})
const computedStyle = computed(() => {

  return {backgroundImage: `url(/img/${props.currentImage ? props.currentImage : 'menus-1'}.jpg)`}
})
</script>

<style scoped>

</style>