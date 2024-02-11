<template>
    <div class="flex flex-col p-8">
      <h1 class="text-4xl font-bold mb-4">Random Meals</h1>
      
  
    </div>
  </template>
  
  <script setup>
  import { computed, onMounted, ref } from "vue";
  import store from "../store";
  import axiosClient from "../axiosClient.js";

  const ingredients = ref([])


onMounted(async() => {
  const response = await axiosClient.get('/list.php?i=list')
  console.log(response.data);
  ingredients.value = response.data
})

  </script>