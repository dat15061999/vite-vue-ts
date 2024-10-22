<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="relative">
    <div class="fixed top-0 left-0 bottom-0 w-[320px] h-screen bg-blue-300">
      <h1
        class="text-3xl text-center text-white font-bold py-6 cursor-pointer"
        @click="$router.push('/')"
      >
        Application
      </h1>
      <nav>
        <ul class="text-center *:pb-4">
          <li>
            <RouterLink
              to="/"
              class="px-20 py-2 text-lg font-medium hover:bg-green-300 hover:text-white cursor-pointer"
              >Home</RouterLink
            >
          </li>
          <li>
            <RouterLink
              to="/about"
              class="px-20 py-2 text-lg font-medium hover:bg-green-300 hover:text-white cursor-pointer"
              >About</RouterLink
            >
          </li>
        </ul>
      </nav>
    </div>
    <div class="ml-[340px] py-8 text-base">
      <RouterView />
    </div>
  </div>
</template>
