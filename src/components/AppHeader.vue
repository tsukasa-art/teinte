<script setup lang="ts">
import appMarkUrl from "../assets/app-mark.svg";

defineProps<{ appDisplayName: string }>();
</script>

<template>
  <header class="header" role="banner">
    <div class="header-inner">
      <div class="header-brand">
        <img class="header-mark" :src="appMarkUrl" alt="" aria-hidden="true" />
        <div class="header-titles">
          <h1 class="title">{{ appDisplayName }}</h1>
        </div>
      </div>
    </div>
    <div class="header-accent" aria-hidden="true" />
  </header>
</template>

<style scoped>
.header {
  position: relative;
  background: linear-gradient(180deg, #35353a 0%, var(--primary) 100%);
  color: #fff;
  padding: 0.85rem 1.25rem 0;
  border-bottom: none;
  flex-shrink: 0;
}

.header-inner {
  max-width: 1200px;
  margin: 0 auto;
  padding-bottom: 0.75rem;
}

.header-brand {
  display: flex;
  align-items: center;
  gap: 0.85rem;
}

/* アプリのアイコンと同じ絵（角丸は 185/824 ≒ 22.5%） */
.header-mark {
  display: block;
  width: 2.5rem;
  height: 2.5rem;
  flex-shrink: 0;
  border-radius: 22.5%;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.35);
}

.header-titles {
  flex: 1;
  min-width: 0;
}

.header-accent {
  height: 3px;
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  border-radius: 2px 2px 0 0;
  /* アイコンの3つの丸と同じ色・同じ比（ベース 55.3：アソート 37.0：アクセント 7.8） */
  background: linear-gradient(
    90deg,
    #afd2f9 0 55.3%,
    #d6b7b2 55.3% 92.3%,
    #637191 92.3% 100%
  );
  opacity: 0.92;
}

.title {
  margin: 0;
  font-size: 1.35rem;
  font-weight: 800;
  letter-spacing: -0.02em;
  line-height: 1.2;
  /* 太字のキャップ高でアイコンより視覚的に上に寄るのを抑える */
  transform: translateY(0.07em);
}
</style>
