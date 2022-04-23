<template>
<div class="dish-container"
    v-for="dish in props.dishes"
    :key="dish.id">
  <p class="dish">{{dish.title}}
    <span class="dish-ingredients">
      {{dish.ingredients}}
    </span></p>

  <p class="dish-price">{{dish.price}}</p>
</div>
</template>

<script setup>
import {defineProps} from "vue";
const props = defineProps({
  dishes:{
    type: Array
  }
})
</script>

<style scoped>

</style>