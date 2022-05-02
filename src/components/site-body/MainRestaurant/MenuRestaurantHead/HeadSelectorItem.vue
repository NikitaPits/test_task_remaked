<template>
<div @click="chooseSelector">
  <h2
      class="head__selector-title">
    <slot></slot>
  </h2>

</div>
</template>

<script setup>
import {defineProps, defineEmits, ref} from "vue";
const emits = defineEmits(['change-menu'])
let chosen = ref(false)
const props = defineProps({
  selector:{
    type:Object
  }
})
emits('change-menu', 'west', 'menus-1')
function chooseSelector() {
  emits('change-menu', props.selector.id)
  chosen.value=!chosen.value
}
</script>

<style scoped>

</style>