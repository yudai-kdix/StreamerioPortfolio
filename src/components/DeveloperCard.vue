<template>
  <article class="card pixel-frame">
    <div class="card-body">
      <div class="avatar" :data-initial="initials" :style="avatarStyle"></div>
      <div class="name">{{ name }}</div>
      <div class="roles">
        <span v-for="r in roles" :key="r" class="badge">{{ r }}</span>
      </div>
      <p class="bio">{{ bio }}</p>
      <div class="actions">
        <a v-if="xUrl" class="icon-btn" :href="xUrl" target="_blank" rel="noreferrer noopener" aria-label="X" title="X">
          <Twitter :size="18" />
        </a>
        <a v-if="portfolioUrl" class="icon-btn" :href="portfolioUrl" target="_blank" rel="noreferrer noopener" aria-label="Portfolio" title="Portfolio">
          <ExternalLink :size="18" />
        </a>
      </div>
    </div>
  </article>
</template>

<script setup>
import { computed } from 'vue';
import { Twitter, ExternalLink } from 'lucide-vue-next';

const props = defineProps({
  icon: { type: String, default: '' },
  name: { type: String, required: true },
  roles: { type: Array, default: () => [] },
  bio: { type: String, default: '' },
  xUrl: { type: String, default: '' },
  portfolioUrl: { type: String, default: '' }
});

const initials = computed(() =>
  (props.name || '')
    .trim()
    .slice(0, 2)
);

const avatarStyle = computed(() => {
  if (!props.icon) return {};
  return {
    backgroundImage: `url(${props.icon})`,
    imageRendering: 'pixelated',
    backgroundSize: 'cover',
    backgroundPosition: 'center',
  };
});
</script>

<style scoped>
.card {
  padding: 16px;
  border-radius: 14px; /* 丸み追加 */
  transition: transform 160ms ease, filter 160ms ease;
}
.card.pixel-frame { overflow: hidden; }
.card:hover {
  transform: translateY(-6px);
  filter: drop-shadow(0 12px 16px rgba(0,0,0,0.45));
}
.card-body { display: grid; gap: 12px; }
.avatar {
  width: 88px; height: 88px;
  border-radius: 20px; /* やや丸い角のピクセル風 */
  margin-top: 6px;
  background: linear-gradient(180deg, rgba(122,199,255,.18), rgba(167,139,250,.18));
  border: 1px solid rgba(255,255,255,.08);
  display: grid; place-items: center;
}
.avatar:not([style*="background-image"])::after {
  content: attr(data-initial);
  font-weight: 700; color: var(--text);
}
.name { font-weight: 700; font-size: 18px; }
.roles { display: flex; flex-wrap: wrap; gap: 6px; }
.bio { color: var(--muted); margin: 6px 0 2px; }
.actions { display: flex; gap: 10px; flex-wrap: wrap; align-items: center; }

.icon-btn {
  width: 36px; height: 36px;
  display: inline-grid; place-items: center;
  color: var(--text);
  background: linear-gradient(180deg, rgba(167,139,250,0.22), rgba(122,199,255,0.12));
  border: 1px solid rgba(255,255,255,0.14);
  border-radius: 10px;
  text-decoration: none;
}
.icon-btn:hover { filter: brightness(1.08) saturate(1.05); }
</style>
