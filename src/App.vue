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
  <main>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita est nihil suscipit, 
      reiciendis quos nulla nobis architecto earum itaque consequatur laboriosam eius mollitia
      optio vitae, delectus quis, non ut consectetur. Lorem ipsum dolor sit amet consectetur adipisicing
       elit. Necessitatibus, doloremque at deleniti quam quaerat ea, optio sapiente in rem omnis, temporibus
        excepturi ex hic voluptate ipsum? Velit error cumque aspernatur.
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita est nihil suscipit, 
      reiciendis quos nulla nobis architecto earum itaque consequatur laboriosam eius mollitia
      optio vitae, delectus quis, non ut consectetur. Lorem ipsum dolor sit amet consectetur adipisicing
       elit. Necessitatibus, doloremque at deleniti quam quaerat ea, optio sapiente in rem omnis, temporibus
        excepturi ex hic voluptate ipsum? Velit error cumque aspernatur.
  </main>
</template>

<script setup>
  import { CheckCircleIcon} from '@heroicons/vue/24/solid'
</script>

<style scoped>

</style>