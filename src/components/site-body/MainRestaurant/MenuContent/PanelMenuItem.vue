<template>

  <p v-bind:class="[props.panelItemState ? 'сuisine__one_active':'сuisine__one']"
      v-on:click="$emit('was-clicked', props.name.id)"
  >
    <slot></slot>
  </p>
</template>

<script setup>
import {defineProps} from "vue";
const props = defineProps({
  name:{value: Object,
    required: true},
  panelItemState:{
    value: Boolean,
    required:true
    }
})
</script>

<style scoped>

</style>