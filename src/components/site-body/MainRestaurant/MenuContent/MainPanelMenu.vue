<template>
  <section>
    <div class="panel-menu__сuisine">
      <panel-menu-item
        v-for="menu in props.menus"
        :menu="menu"
        :panelItemState="menu.id === activeElem.id"
        :key="menu.id"
        @was-clicked="refreshMenuItems"
      >
        {{ menu.name }}
      </panel-menu-item>
    </div>
    <menu-page-main 
      class="panel_menu__menu"
      :menus="props.menus"
      :activeElem="activeElem"
    />
  </section>
</template>

<script setup>
import { ref, toRefs, watch } from "vue"; // eslint-disable-line
import PanelMenuItem from "@/components/site-body/MainRestaurant/MenuContent/PanelMenuItem";
import MenuPageMain from "@/components/site-body/MainRestaurant/MenuContent/MenuPage/MenuPageMain";
import {defineProps} from "vue";
const props = defineProps({
  menus: {
    value: Array,
  }
});

function getStartElem(val) {
  return (val && val.length) ? val[0] : {};
}
const activeElem = ref(getStartElem());

watch(() => { return props.menus; }, (val) => {
  activeElem.value = getStartElem(val);
});

function refreshMenuItems(id) {
  activeElem.value = props.menus.find((menu) => {
    return menu.id === id;
  });
}
</script>

<style scoped>
</style>