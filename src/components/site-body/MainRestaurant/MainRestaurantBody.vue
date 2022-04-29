<template>
  <div>
    <menu-restaurant-head
        @change-menu="changeMenu"
        class="menu-restaurant__head"/>
    <menu-restaurant-main-container
        :menus="menus"
        class="menus-restaurant__main main-container"/>
    <div class="foot-book">
      <my-button class="site-header__button">BOOK A TABLE</my-button>
    </div>
  </div>
</template>
<script setup>
import MenuRestaurantHead from "@/components/site-body/MainRestaurant/MenuRestaurantHead/MenuRestaurantHead";
import MenuRestaurantMainContainer from "@/components/site-body/MainRestaurant/MenuContent/MenuRestaurantMainContainer";
import {ref} from "vue";
import MyButton from "@/components/UI/MyButton";
import {onMounted} from "vue";
import api from "@/api/main";

const JSON_CONTENT = "/6c1b1d6b-1978-49bf-81db-563d073fdaf5";
const jsonContent = ref([])
let menus = ref()
onMounted(async () => {
  const {data} = await api.get(JSON_CONTENT);
  jsonContent.value = data;
  menus.value=jsonContent.value[0].content
});

function changeMenu(menuId) {
  jsonContent.value.forEach(element => {
    if(element.id === menuId){
      menus.value = element.content
    }
  });
}
</script>

<style scoped>

</style>