<template>
  <div class="selector__list-f">
    <div>
      <h6 v-bind:class="[picked?'list-f__one_active':'list-f__one']"
          @click="isPicked">
        <slot></slot>
      </h6>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue";
import {defineEmits, defineProps} from "vue";

const props = defineProps({
  filter:{
    type:Object
  }
})
let picked = ref(props.filter.state);
const emits = defineEmits(['picked-filter'])

function isPicked() {
  picked.value = !picked.value
  emits('picked-filter', picked.value, props.filter.id)
}

</script>

<style scoped>
</style>