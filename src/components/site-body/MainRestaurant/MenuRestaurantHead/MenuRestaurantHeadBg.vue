<template>
  <div class="head__bg"
       :style="computedStyle">
  </div>
</template>

<script setup>
import {computed, defineProps} from "vue";

const props = defineProps({
  activeChooser: {
    type: String
  }
})
const computedStyle = computed(() => {

  return {backgroundImage: `url(/img/${props.activeChooser ? props.activeChooser : 'menus-1'}.jpg)`}
})
</script>

<style scoped>

</style>