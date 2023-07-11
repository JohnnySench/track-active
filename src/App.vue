<template>
  <TheHeader 
    @go-to-timeline="goTo(PAGE_TIMELINE)"
    @go-to-progress="goTo(PAGE_PROGRESS)"
    />
  <main class="flex flex-grow flex-col">
      <TheProgress v-show="currentPage === PAGE_PROGRESS"/>
      <TheActivities v-show="currentPage === PAGE_ACTIVITIES"/>
      <TheTimeline v-show="currentPage === PAGE_TIMELINE"/>
  </main>
  <TheNav :current-page="currentPage" @navigate="goTo($event)"/>
</template>

<script setup>
  import TheHeader from './components/TheHeader.vue';
  import TheNav from './components/TheNav.vue';
  import { normalizePageHash } from './functions';
  import TheActivities from './pages/TheActivities.vue';
  import TheProgress from './pages/TheProgress.vue';
  import TheTimeline from './pages/TheTimeline.vue';
  import {PAGE_ACTIVITIES, PAGE_PROGRESS, PAGE_TIMELINE} from './constants';
  import { ref } from 'vue';

  const currentPage = ref(normalizePageHash())


  

  function goTo(page) {
    currentPage.value = page
  }

</script>
