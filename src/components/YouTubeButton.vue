<template>
    <a
      :href="href"
      target="_blank"
      class="inline-block bg-red-600 text-white py-2 px-4 rounded-lg hover:bg-red-700 transition-all duration-200"
    >
      <slot>YouTube</slot>
    </a>
  </template>
  
  <script setup>
  const props = defineProps({
    href: String
  })
  </script>