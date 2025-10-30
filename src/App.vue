<template>
  <AppHeader />
  <main>
    <SlideEmbed />
    <DeveloperList />
  </main>
  <AppFooter />
</template>

<script setup>
import AppHeader from './components/AppHeader.vue';
import SlideEmbed from './components/SlideEmbed.vue';
import DeveloperList from './components/DeveloperList.vue';
import AppFooter from './components/AppFooter.vue';
</script>

<style scoped>
main { display: block; }
</style>

