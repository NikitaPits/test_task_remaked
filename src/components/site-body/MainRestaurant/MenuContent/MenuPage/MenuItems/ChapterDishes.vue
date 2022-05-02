<template>
  <div class="dish-container"
       v-for="dish in props.dishes"
       :key="dish.id">
    <p class="dish"
       :style="isPassive(dish) ? computedStyle: ''"
    >{{ dish.title }}
      <span class="dish-ingredients"
            :style="computedStyle"
      >
      {{ dish.ingredients }}
    </span>
    </p>

    <p class="dish-price">{{ dish.price }}</p>
  </div>
</template>

<script setup>
import {defineProps, toRefs} from "vue";

const props = defineProps({
  dishes: {
    type: Array
  },
  filters: {
    type: Array
  }
})
const computedStyle = {color: `#d0cecd`}
const { filters } = toRefs(props)

function isPassive(dish) {
  return (filters.value || []).some(filter => {
    return !dish[filter.id] && filter.state;
  });
}
</script>

<style scoped>

</style>