<template>
  <div class="flex flex-col p-8">
    <input type="text" class="rounded border-2 border-gray-200 w-full" placeholder="Search for Meals" />

    <div class="flex gap-2 justify-center mt-2">
      <router-link :to="{name: 'byLetter', params: {letter}}" v-for="letter in letters" :key="letter">
        {{ letter }}
      </router-link>
    </div>

    <pre>{{ ingredients }}</pre>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import axiosClient from '../axiosClient';

const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split("");
const ingredients = ref([])

onMounted(async () => {
  const response = await axiosClient.get('/list.php?i=list')
  console.log(response.data)
  ingredients.value = response.data
})
</script>