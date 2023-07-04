<template>
  <header class="sticky top-0 z-20 flex items-center justify-between border-b bg-white p-3">
    <a href="#">
      <img src="./assets/logo.png" alt="logo" class="h-9">
    </a>
    <a href="#" class="text-md">
      <div v-if="false" class="flex items-center gap-1">
        Day Complete!
        <CheckCircleIcon class="h-7 text-green-500"/>
      </div>
      <div v-else class="flex items-center gap-1">
        <div>Progress: <span class="font-mono">20%</span></div>
        <div class="h-3 w-3 rounded-full bg-red-500"></div>
      </div>
    </a>
  </header>
  <main class="flex flex-grow flex-col">
      Main
  </main>
  <nav class="sticky bottom-0 bg-white">
    <ul class="flex justify-around items-center">
      <li class="flex-1">
        <a href="#timeline" class="flex flex-col items-center p-2 text-xs capitalize">
          <ClockIcon class="h-6 w-6"/>timeline
        </a>
      </li>
      <li class="flex-1">
        <a href="#activites" class="flex flex-col items-center p-2 text-xs capitalize">
          <ListBulletIcon class="h-6 w-6"/>activites
        </a>
      </li>
      <li class="flex-1">
        <a href="#progress" class="flex flex-col items-center p-2 text-xs capitalize">
          <ChartBarIcon class="h-6 w-6"/>progress
        </a>
      </li>
    </ul>
  </nav>
</template>

<script setup>
  import { CheckCircleIcon} from '@heroicons/vue/24/solid'
  import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'
</script>

<style scoped>

</style>