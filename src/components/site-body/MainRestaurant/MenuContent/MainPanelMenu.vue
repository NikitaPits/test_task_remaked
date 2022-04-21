<template>
  <section>
    <div class="panel-menu__сuisine">
    <panel-menu-item
        v-for="name in props.names"
        :name="name"
        :panelItemState = "name.id===activeId"
        :key="name.id"
    @was-clicked="refreshMenuItems">
      {{name.name}}
  </panel-menu-item>
  </div>
    <menu-page-main class="panel_menu__menu"
    :actualName="actualName"
    />
  </section>
</template>

<script setup>
import {ref} from "vue";
import PanelMenuItem from "@/components/site-body/MainRestaurant/MenuContent/PanelMenuItem";
import MenuPageMain from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageMain";
import {defineProps} from "vue";
const props = defineProps({
  names: {
    value: Array,
    required: true,
  }
})
let activeId = ref('1');
let actualName = ref('1')
    function refreshMenuItems(n){
      activeId.value = n;
      actualName.value = props.names[activeId.value-1].name
      console.log(actualName.value)
    }


</script>

<style scoped>
</style>