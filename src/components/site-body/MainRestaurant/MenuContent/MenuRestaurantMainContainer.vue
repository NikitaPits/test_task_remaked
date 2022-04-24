<template>
  <div>
    <main-description class="main__description"/>
    <main-panel-menu
        :menus="props.menus"
        class="panel-menu"
    >

    </main-panel-menu>
  </div>
</template>

<script setup>
import MainDescription from "@/components/site-body/MainRestaurant/MenuContent/MainDescription";
import MainPanelMenu from "@/components/site-body/MainRestaurant/MenuContent/MainPanelMenu";
import {defineProps} from "vue";

const props = defineProps({ // eslint-disable-line
  menus: {
    value: Object,
    required: true,
  }
});
</script>

<style scoped>
</style>