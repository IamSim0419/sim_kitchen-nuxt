<script lang="ts" setup>
import HeaderApp from "~/components/HeaderApp.vue";
</script>

<template>
  <div>
    <HeaderApp />
    <slot />
  </div>
</template>

<style scoped>
@reference 'tailwindcss';
</style>
