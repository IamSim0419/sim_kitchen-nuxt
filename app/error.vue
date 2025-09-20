<script setup lang="ts">
import type { NuxtError } from "#app";

defineProps({
  error: Object as () => NuxtError,
});
</script>

<template>
  <section class="flex min-h-screen flex-col items-center justify-center">
    <h1 class="mb-2 text-5xl font-bold">
      {{ error?.statusCode }}
    </h1>
    <p class="mb-10 text-5xl">{{ error?.statusMessage }}</p>
    <UButton to="/"> Go home </UButton>
  </section>
</template>
