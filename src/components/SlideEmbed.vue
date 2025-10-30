<template>
  <section id="slides">
    <div class="container">
      <h2 class="title-pixel" style="font-size:16px; opacity:.9; margin: 0 0 14px;">Slides</h2>
      <div class="slide-wrap pixel-frame">
        <div class="slide-frame">
          <iframe :src="url" allow="fullscreen" allowfullscreen></iframe>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { FIGMA_SLIDE_URL } from '../config';
const url = FIGMA_SLIDE_URL;
</script>

<style scoped>
.slide-wrap { padding: 10px; }
</style>

