<template>
  <div
    class="relative h-full w-full bg-gradient-to-b from-[#0c0b1d] via-[#0f1433] to-[#0c0b1d] text-slate-200 transition-colors"
  >
    <div
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 overflow-hidden"
    >
      <div class="anime-aurora blur-[80px]" />
      <div class="anime-aurora anime-aurora--2 blur-[90px]" />
      <div class="anime-grid" />
    </div>
    <div class="relative m-auto flex h-fit min-h-screen flex-col items-center">
      <Navbar />
      <FoundingMemberNotice></FoundingMemberNotice>
      <!-- 多一层内容的横向内边距是为了和 Navbar 对齐 -->
      <div class="flex w-full flex-1 px-5">
        <div class="mx-auto flex w-full max-w-screen-xl flex-1">
          <NuxtPage />
        </div>
      </div>
      <Footer></Footer>
    </div>
  </div>
  <UserMenu />
</template>

<script setup lang="ts">
import FoundingMemberNotice from "../components/FoundingMemberNotice.vue";
</script>

<style scoped>
.anime-aurora {
  position: absolute;
  inset: -10% 20% auto;
  height: 40%;
  min-width: 40vw;
  background: radial-gradient(circle at 30% 40%, rgba(255, 143, 234, 0.4), transparent 40%),
    radial-gradient(circle at 70% 60%, rgba(116, 217, 255, 0.35), transparent 45%),
    radial-gradient(circle at 50% 20%, rgba(133, 87, 255, 0.35), transparent 40%);
  opacity: 0.8;
  transform: rotate(-6deg);
}

.anime-aurora--2 {
  inset: auto 5% -20% 5%;
  height: 35%;
  min-width: 60vw;
  background: radial-gradient(circle at 20% 50%, rgba(255, 226, 143, 0.28), transparent 40%),
    radial-gradient(circle at 80% 60%, rgba(255, 126, 176, 0.32), transparent 45%),
    radial-gradient(circle at 60% 35%, rgba(126, 206, 255, 0.28), transparent 38%);
  transform: rotate(4deg);
}

.anime-grid {
  position: absolute;
  inset: 0;
  background-image: linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
  background-size: 120px 120px;
  mask-image: radial-gradient(circle at 20% 20%, rgba(255, 255, 255, 0.85), transparent 60%),
    radial-gradient(circle at 80% 50%, rgba(255, 255, 255, 0.65), transparent 65%),
    radial-gradient(circle at 50% 90%, rgba(255, 255, 255, 0.4), transparent 70%);
  opacity: 0.5;
}
</style>
