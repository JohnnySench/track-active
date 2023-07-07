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
  import { PAGE_TIMELINE, PAGE_ACTIVITIES, PAGE_PROGRESS } from '../constants'
  import { ref } from 'vue';

  import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'
    
  const navItems = {
    [PAGE_TIMELINE]: ClockIcon,
    [PAGE_ACTIVITIES]: ListBulletIcon,
    [PAGE_PROGRESS]: ChartBarIcon
  }
  const currentPage = ref(normalizePageHash())


  function normalizePageHash() {
    const hash = window.location.hash.slice(1);

    if (Object.keys(navItems).includes(hash)) {
      return hash
    }

    window.location.hash = PAGE_TIMELINE;

    return PAGE_TIMELINE
  }

</script>