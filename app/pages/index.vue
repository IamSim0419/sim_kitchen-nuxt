<script lang="ts" setup>
import { type RecipeResponse } from "~~/types/types";

definePageMeta({
  layout: "default",
});

const { data, error } = await useFetch<RecipeResponse>(
  "https://dummyjson.com/recipes"
);

const recipesData = data.value?.recipes.slice(16, 28);

useSeoMeta({
  title: "Sim's Kitchen",
  description: "Recipes for you to cook!",
  ogTitle: "Sim's Kitchen",
  ogDescription: "Recipes for you to cook!",
  ogImage: "/nuxt-course-hero.png",
  ogUrl: `http:localhost:3000`,
  twitterTitle: "Sim's Kitchen",
  twitterDescription: "Recipes for you to cook!",
  twitterImage: "/nuxt-course-hero.png",
  twitterCard: "summary",
});

useHead({
  htmlAttrs: {
    lang: "en",
  },
  link: [
    {
      rel: "icon",
      type: "image/png",
      href: "/cook-hat.png",
    },
  ],
});
</script>

<template>
  <main class="px-4">
    <section class="bg-neutral-100">
      <div
        class="container mx-auto flex flex-col lg:flex-row items-center py-20 gap-10"
      >
        <div class="flex-1 order-2 lg:order-1 text-center lg:text-left">
          <h1 class="text-4xl lg:text-6xl font-extrabold mb-6 text-balance">
            Master the Kitchen with Ease: Unleash Your Inner Chef Today!
          </h1>
          <p class="text-xl lg:text-2xl mb-8 text-balance">
            Discover recipes helping you to find the easiest way to cook.
          </p>
          <UButton
            class="text-2xl text-white"
            to="#recipes"
            label="Browse Recipes"
          />
        </div>
        <div class="flex-1 order-1 lg:order-2">
          <NuxtImg
            sizes="xs:100vw sm:667px"
            src="/food.png"
            format="webp"
            densities="x1"
            alt=""
          />
        </div>
      </div>
    </section>

    <section id="recipes" class="py-20 container mx-auto">
      <h2 class="text-3xl lg:text-5xl font-medium mb-2">
        Discover, Create, Share
      </h2>
      <p class="text-lg lg:text-xl mb-8">Check out our most popular recipes!</p>
      <div
        v-if="!error"
        class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-4 gap-y-8"
      >
        <RecipeCard v-for="recipe in recipesData" :recipe="recipe" />
      </div>
      <p v-else class="text-xl text-red-400">
        Opps, something went wrong. Please try again later
      </p>
    </section>
    <!-- <section class="bg-[#f1f1f1] py-20">
      <SignupForm />
    </section> -->
  </main>
</template>

<style scoped>
@reference 'tailwindcss';
</style>
