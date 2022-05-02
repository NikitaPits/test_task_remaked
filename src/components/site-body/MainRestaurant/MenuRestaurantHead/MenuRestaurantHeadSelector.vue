<template>
  <div>
    <div class="main-container">
      <head-selector-item
          v-for="selector in jsonSelectors"
          :key="selector.id"
          :selector="selector"
          @change-menu="change"
          v-bind:class="[currentId===selector.id?'selector__one selector__one-active':'selector__one']"
      >
        {{ selector.name }}
      </head-selector-item>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue"
import {defineEmits} from "vue";

import jsonSelectors from '/src/assets/jsonContent/jsonSelectors.json'
import HeadSelectorItem from "@/components/site-body/MainRestaurant/MenuRestaurantHead/HeadSelectorItem";

const emits = defineEmits(['change-menu'])

let currentId = ref('')

function change(id) {
  currentId.value = id;
  emits('change-menu', currentId.value)
}

</script>
<style scoped>
</style>