<template>
  <section id="team">
    <div class="container">
      <h2 class="title-pixel" style="font-size:18px; margin:0 0 12px;">KITnow++</h2>
      <div class="pixel-frame team-panel">
        <p class="team-text">
          KINDAI Info-Tech HUB（<a href="https://kithub.jp/" target="_blank" rel="noreferrer noopener">kithub.jp</a>）、
          watnow（<a href="https://x.com/watnows" target="_blank" rel="noreferrer noopener">@watnows</a>）、
          Rig++（<a href="https://rigpp.sakura.ne.jp/wp/" target="_blank" rel="noreferrer noopener">rigpp.sakura.ne.jp</a>）の
          <strong>3つの</strong>学生団体の所属者がいるチームです！
        </p>
        <div class="links">
          <a class="badge link" href="https://kithub.jp/" target="_blank" rel="noreferrer noopener">
            KINDAI Info-Tech HUB <ExternalLink :size="14" />
          </a>
          <a class="badge link" href="https://x.com/watnows" target="_blank" rel="noreferrer noopener">
            watnow <ExternalLink :size="14" />
          </a>
          <a class="badge link" href="https://rigpp.sakura.ne.jp/wp/" target="_blank" rel="noreferrer noopener">
            Rig++ <ExternalLink :size="14" />
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ExternalLink } from 'lucide-vue-next';
</script>

<style scoped>
.team-panel { padding: 16px; border-radius: 12px; }
.team-text { margin: 4px 0 12px; line-height: 1.8; color: var(--text); }
.links { display: flex; flex-wrap: wrap; gap: 8px; }
.link { display: inline-flex; align-items: center; gap: 6px; text-decoration: none; }
.link:hover { filter: brightness(1.07); }
</style>

