<template>
  <section id="developers">
    <div class="container">
      <h2 class="title-pixel" style="font-size:18px; margin:0 0 14px;">開発者について</h2>
      <div class="grid">
        <DeveloperCard
          v-for="(d, i) in developers"
          :key="i"
          v-bind="d"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
// ルート `app/developer.json` を直接取り込み
import developersData from '../../developer.json';
import DeveloperCard from './DeveloperCard.vue';

const developers = Array.isArray(developersData) ? developersData : [];
</script>
