<template>
    <nav class="sticky bottom-0 bg-white">
    <ul class="flex justify-around items-center">
      <NavItem 
        @click="currentPage = page"  
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
  import { ref } from 'vue';

  import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'
    
  const navItems = {
    timeline: ClockIcon,
    activites: ListBulletIcon,
    progress: ChartBarIcon
  }
  const currentPage = ref('activites')

</script>