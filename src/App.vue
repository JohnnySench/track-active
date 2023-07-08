<template>
  <TheHeader/>
  <main class="flex flex-grow flex-col">
      <TheProgress v-show="currentPage === PAGE_PROGRESS"/>
      <TheActivities v-show="currentPage === PAGE_ACTIVITIES"/>
      <TheTimeline v-show="currentPage === PAGE_TIMELINE"/>
  </main>
  <TheNav :current-page="currentPage" @navigate="currentPage = $event"/>
</template>

<script setup>
  import TheHeader from './components/TheHeader.vue';
  import TheNav from './components/TheNav.vue';
  import {PAGE_ACTIVITIES, PAGE_PROGRESS, PAGE_TIMELINE} from './constants';
  import TheActivities from './pages/TheActivities.vue';
  import TheProgress from './pages/TheProgress.vue';
  import TheTimeline from './pages/TheTimeline.vue';

  import { ref } from 'vue';

  const currentPage = ref(normalizePageHash())


  function normalizePageHash() {
    const hash = window.location.hash.slice(1);

    if ([PAGE_TIMELINE, PAGE_ACTIVITIES, PAGE_PROGRESS].includes(hash)) {
      return hash
    }

    window.location.hash = PAGE_TIMELINE;

    return PAGE_TIMELINE
  }
</script>
