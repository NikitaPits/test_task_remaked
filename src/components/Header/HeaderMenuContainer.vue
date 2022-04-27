<template>
  <div>
    <header-menu-list class="site-header__menu-list"
                      :class="{'site-header__menu-list_active': needToOpen }"/>
    <my-button
        class="site-header__button"
        :class="{'site-header__button_active': needToOpen }"
    >
      book a table
    </my-button>
    <div
        @click="openMenu"
        class="mob_burger"
        :class="{'mob_burger_active': needToOpen }">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </div>
</template>

<script setup>
import HeaderMenuList from "@/components/Header/HeaderMenuList";
import MyButton from "@/components/UI/MyButton";
import {ref} from "vue";

let needToOpen = ref(false)

function openMenu() {
needToOpen.value=!needToOpen.value
}
</script>

<style scoped>

</style>