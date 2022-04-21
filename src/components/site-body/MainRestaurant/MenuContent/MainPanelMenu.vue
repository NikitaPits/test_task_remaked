<template>
  <section>
    <div class="panel-menu__сuisine">
      <panel-menu-item
        v-for="name in props.names"
        :name="name"
        :panelItemState="name.id === activeElem.id"
        :key="name.id"
        @was-clicked="refreshMenuItems"
      >
        {{ name.name }}
      </panel-menu-item>
    </div>
    <menu-page-main 
      class="panel_menu__menu"
      :actualName="activeElem.name"
    />
  </section>
</template>

<script setup>
import { ref, toRefs, watch } from "vue"; // eslint-disable-line
import PanelMenuItem from "@/components/site-body/MainRestaurant/MenuContent/PanelMenuItem";
import MenuPageMain from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageMain";
import {defineProps} from "vue";
const props = defineProps({
  names: {
    value: Array,
    default: () => (
      [
        { name: 'à la carte menu2222', id: '1' },
        {name: 'rose brunch', id: '2'},
        {name: 'cocktails', id: '3'},
        {name: 'desserts', id: '4'},
      ]
    ),
  }
});

function getStartElem(val) {
  return (val && val.length) ? val[0] : {};
}
const activeElem = ref(getStartElem());

watch(() => { return props.names; }, (val) => {
  activeElem.value = getStartElem(val);
});

function refreshMenuItems(id) {
  activeElem.value = props.names.find((name) => {
    return name.id === id;
  });
}
</script>

<style scoped>
</style>