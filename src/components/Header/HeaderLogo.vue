<template>
  <div class="site-header__logo">
<site-logo
    :color="'#fff'"/>
    <div class="site-header__logo-text">
      <span>
        {{ 'at ' }}
      </span>
      {{ ' THE SHARD' }}
    </div>
  </div>
</template>

<script setup>
import SiteLogo from "@/components/UI/SiteLogo";
</script>

<style scoped>
</style>