<template>
    <nav class="sticky bottom-0 bg-white">
    <ul class="flex justify-around items-center">
      <NavItem 
        @click="emit('navigate', page)"  
        v-for="(icon, page) in navItems" 
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
  import { PAGE_PROGRESS, PAGE_TIMELINE, PAGE_ACTIVITIES } from '../constants';
  import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'
    
  defineProps(['currentPage'])

  const emit = defineEmits(['navigate'])

  const navItems = {
    [PAGE_TIMELINE]: ClockIcon,
    [PAGE_ACTIVITIES]: ListBulletIcon,
    [PAGE_PROGRESS]: ChartBarIcon
  }

</script>