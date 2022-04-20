<template>
<h3 class="top__title">
  <slot>{{props.actualName}}</slot>
</h3>
</template>

<script setup>
import {defineProps } from "vue";

const props = defineProps({
  actualName:{
    type:String,
    required: true
  }
})
</script>

<style scoped>
</style>