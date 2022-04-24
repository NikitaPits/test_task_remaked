<template>
  <header
      class="site-header">
    <div
        class="site-header__header-wrapper main-container">
      <header-logo/>
      <header-menu-container
          class="site-header__header-menu-container"></header-menu-container>
    </div>
  </header>
</template>

<script setup>
import HeaderMenuContainer from "@/components/Header/HeaderMenuContainer";
import HeaderLogo from "@/components/Header/HeaderLogo";
</script>

<style scoped>

</style>