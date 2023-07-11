<template>
    <nav class="sticky bottom-0 bg-white">
    <ul class="flex justify-around items-center">
      <NavItem 
        @click="emit('navigate', page)"  
        v-for="(icon, page) in NAV_ITEMS" 
        :key="page" 
        :href="`#${page}`" 
        :class="{'bg-gray-200 pointer-events-none': page === currentPage}">
        <component 
          :is="icon" 
          class="w-6 h-6"/> {{ page }}
      </NavItem>
    </ul>
  </nav>
</template>

<script setup>
  import NavItem from './NavItem.vue';
  import { NAV_ITEMS } from '../constants';  
    
  defineProps(['currentPage'])

  const emit = defineEmits(['navigate'])

  

</script>