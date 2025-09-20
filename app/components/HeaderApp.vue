<script lang="ts" setup></script>

<template>
  <header class="shadow-md w-full px-4 py-2">
    <div class="container mx-auto flex items-center justify-between">
      <NuxtLink to="/" class="flex items-center">
        <NuxtImg
          format="webp"
          width="56px"
          densities="x1"
          src="/cook-hat.png"
          alt="logo"
        />
        <span class="text-xl lg:text-2xl">Sim's Kitchen</span>
      </NuxtLink>
      <nav>
        <ul class="flex items-center gap-6 text-lg lg:text-xl">
          <li>
            <NuxtLink to="/">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about">About</NuxtLink>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style scoped>
@reference 'tailwindcss';
</style>
