<template>
  <header class="header">
    <div class="container row">
      <div class="brand">
        <span class="title-pixel">Streamerio</span>
      </div>
      <nav class="nav">
        <a class="btn" :href="unityHref" target="_blank" rel="noreferrer noopener" title="unityroom でプレイ">
          <Gamepad2 :size="16" />
          <span>unityroom</span>
        </a>
      </nav>
    </div>
  </header>
  <div class="header-space" />
  
</template>

<script setup>
import { UNITYROOM_URL } from '../config';
import { computed } from 'vue';
import { Gamepad2 } from 'lucide-vue-next';

const unityHref = computed(() => UNITYROOM_URL && UNITYROOM_URL.length > 0 ? UNITYROOM_URL : 'https://unityroom.com/');
</script>

<style scoped>
.header {
  position: sticky;
  top: 0; z-index: 20;
  backdrop-filter: saturate(140%) blur(8px);
  background: linear-gradient(180deg, rgba(15,18,25,0.9), rgba(15,18,25,0.6));
  border-bottom: 1px solid rgba(255,255,255,0.08);
}
.header-space { height: 0; }
.row { display: flex; align-items: center; justify-content: space-between; padding: 14px 0; }
.brand { font-size: 18px; color: var(--text); }
.nav { display: flex; gap: 10px; align-items: center; }
</style>
