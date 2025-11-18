<template>
  <div
    class="w-full flex-col pt-24"
    id="features"
  >
    <CommonTitle
      title="Earthworm · 二次元特化"
      :description="['把刷番体验搬进学习流程，让课程、语境和互动都与 ACG 文化联动。']"
    />
    <section class="py-16">
      <div class="grid grid-cols-1 gap-6 md:mt-8 md:grid-cols-2 md:gap-8 lg:grid-cols-3">
        <template
          v-for="(feItem, feIndex) in FEATURES"
          :key="feIndex"
        >
          <div
            class="anime-card flex items-start gap-4 bg-gradient-to-b from-white/10 via-white/5 to-transparent text-slate-100"
          >
            <div
              class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl bg-gradient-to-br from-fuchsia-400/60 to-sky-300/60 text-white shadow-even-lg"
            >
              <UIcon
                :name="feItem.icon"
                class="h-6 w-6"
              />
            </div>

            <div>
              <h2 class="text-lg font-bold text-white">
                {{ feItem.title }}
              </h2>

              <p class="mt-2 text-sm leading-6 text-slate-200/80">
                {{ feItem.desc }}
              </p>
            </div>
          </div>
        </template>
      </div>
    </section>
  </div>
  <CommonDivider />
</template>

<script setup lang="ts">
const FEATURES = [
  {
    icon: "i-ph-television-simple-fill",
    title: "番剧语境精读",
    desc: "从热播番剧挑选高频台词、吐槽和梗，用熟悉的剧情串起语法和词汇，像复盘剧情一样复现句式。",
  },
  {
    icon: "i-ph-microphone-stage-fill",
    title: "声优口癖跟读",
    desc: "热门角色的招牌口癖、战斗宣言、日常碎碎念都能切片练习，跟着原声节奏做 shadowing。",
  },
  {
    icon: "i-ph-music-notes-fill",
    title: "OP / ED 粒度练习",
    desc: "拆分歌词、押韵和转音，逐句精听并复述，让你在哼主题曲时顺便巩固句式和发音。",
  },
  {
    icon: "i-ph-sparkle-fill",
    title: "角色人设词库",
    desc: "给角色、阵营、CP、梗词打标签，一键筛选对应词组，随手练习也能复盘设定细节。",
  },
  {
    icon: "i-ph-chats-fill",
    title: "漫展生存口语",
    desc: "加入问路、排队、合影、交换推特等常用句库，随时复习 cosplay 场景必备表达。",
  },
  {
    icon: "i-ph-cards-fill",
    title: "收藏卡与成就",
    desc: "用角色主题的收藏卡、徽章和连刷天数点亮你的个人主页，学习成果像抽卡一样可视化。",
  },
];
</script>

<style scoped></style>
