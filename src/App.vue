<script setup lang="ts">
import { RouterView } from 'vue-router'
import TopBar from '@/components/TopBar.vue'
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <TopBar />
    <main>
      <RouterView />
    </main>
  </div>
</template>
