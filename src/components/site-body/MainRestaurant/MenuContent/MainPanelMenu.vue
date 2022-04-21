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
    default: function (){
      return  [
        {name: 'à la carte menu', id: '1'},
        {name: 'rose brunch', id: '2'},
        {name: 'cocktails', id: '3'},
        {name: 'desserts', id: '4'},
      ]
    }
  }
})
let activeId = ref('1');
console.log(props.names)
let actualName = ref(props.names[0].name)
    function refreshMenuItems(n){
      activeId.value = n;
      actualName.value = props.names[activeId.value-1].name
    }


</script>

<style scoped>
</style>