<template>
<div class="bg-gray-100 h-full">
  <header class="bg-white shadow h-16 flex justify-between items-stretch items-center">
    <router-link :to="{name: 'home'}" class="inline-flex items-center h-full px-5 ">
      Home
    </router-link>
    <div class="flex items-center gap-1">
      <router-link :to="{name:'byName'}" class="inline-flex items-center px-2 h-full transition-colors hover:bg-purple-100 cursor-pointer">
        Search Meals
      </router-link>
      <router-link :to="{name:'byLetter'}" class="inline-flex items-center px-2 h-full transition-colors hover:bg-purple-100 cursor-pointer">
        Meals By Letter
      </router-link>
      <router-link :to="{name:'byIngredient'}" class="inline-flex items-center px-2 h-full transition:-col{name:byName}rs hover:bg-purple-100 cursor-pointer">
        Meals By ingredients
      </router-link>
    </div>
  </header>
  <main>
    <RouterView />
  </main>
</div>
</template>

<script setup>
import { RouterView } from 'vue-router';


</script>
