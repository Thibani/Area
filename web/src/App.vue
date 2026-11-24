<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header class="flex items-center gap-6 border-b border-gray-200 p-4">
    <span class="text-xl font-bold">AREA</span>
    <nav class="flex gap-4">
      <RouterLink to="/" class="hover:underline">Home</RouterLink>
      <RouterLink to="/about" class="hover:underline">About</RouterLink>
    </nav>
  </header>
  <main class="p-4">
    <RouterView />
  </main>
</template>
