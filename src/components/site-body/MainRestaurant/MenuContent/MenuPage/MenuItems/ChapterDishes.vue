<template>
  <div class="dish-container"
       v-for="dish in props.dishes"
       :key="dish.id">
    <p class="dish"
       :style="[dish.isVegan && props.filters[0] || dish.nutsContain && props.filters[1] ? computedStyle: '']"
    >{{ dish.title }}
      <span class="dish-ingredients"
            :style="computedStyle"
      >
      {{ dish.ingredients }}
    </span></p>

    <p class="dish-price">{{ dish.price }}</p>
  </div>
</template>

<script setup>
import {defineProps} from "vue";
import {computed} from "vue";

const props = defineProps({
  dishes: {
    type: Array
  },
  filters: {
    type: Array
  }
})
const computedStyle = computed(() => {

  return {color: `#d0cecd`}
})
</script>

<style scoped>

</style>