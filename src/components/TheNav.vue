<template>
    <nav class="sticky bottom-0 bg-white">
    <ul class="flex justify-around items-center">
      <NavItem  v-for="(icon, page) in navItems" :key="page" :href="`#${page}`">
        <component :is="icon" class="w-6 h-6"/> {{ page }}
      </NavItem>
    </ul>
  </nav>
</template>

<script setup>
import NavItem from './NavItem.vue';

import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'
    
    const navItems = {
        timeline: ClockIcon,
        activites: ListBulletIcon,
        progress: ChartBarIcon
    }
</script>