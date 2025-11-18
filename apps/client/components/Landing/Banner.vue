<template>
  <section
    class="relative overflow-hidden pt-28 text-gray-100"
    id="home"
  >
    <div class="pointer-events-none absolute inset-0 opacity-60">
      <div
        class="absolute inset-10 rounded-[32px] border border-white/10 bg-gradient-to-b from-white/5 via-fuchsia-500/10 to-transparent blur-3xl"
      />
    </div>
    <div class="relative mx-auto my-5 text-center">
      <p
        class="mx-auto w-fit rounded-full border border-white/10 bg-white/10 px-4 py-1 text-xs uppercase tracking-[0.28em] text-fuchsia-100 shadow-even-md"
      >
        anime immersion
      </p>
      <h2
        class="mt-4 bg-gradient-to-r from-fuchsia-300 via-purple-200 to-sky-200 bg-clip-text text-3xl font-extrabold tracking-tight text-transparent lg:text-4xl xl:text-5xl"
      >
        把英语练习变成刷番日常
      </h2>

      <div class="mt-6 text-sm md:text-base xl:text-lg">
        <p class="pt-2 text-center text-slate-100/90 lg:text-xl">
          用<span class="text-fuchsia-200">番剧台词</span>、<span class="text-fuchsia-200"
            >声优口癖</span
          >、<span class="text-fuchsia-200">OP/ED</span>歌词做素材， 让句子练习直接连通你的爱好圈。
        </p>
        <p class="pt-2 text-center text-slate-100/80 lg:text-xl">
          配合 <span class="text-fuchsia-200">连词成句</span>、<span class="text-fuchsia-200"
            >i + 1</span
          >
          和 <span class="text-fuchsia-200">肌肉记忆复现</span>，把单词背诵变成刷剧情的衍生乐趣。
        </p>
      </div>

      <div
        class="mt-6 flex flex-wrap justify-center gap-3 text-xs uppercase tracking-[0.2em] text-fuchsia-50"
      >
        <span class="anime-chip bg-gradient-to-r from-fuchsia-400/60 to-purple-500/60"
          >番剧语境</span
        >
        <span class="anime-chip bg-gradient-to-r from-sky-400/60 to-teal-300/60">声优台词</span>
        <span class="anime-chip bg-gradient-to-r from-amber-300/60 to-pink-400/60">OP & ED</span>
      </div>
    </div>
    <div class="relative my-10 flex flex-wrap items-center justify-center gap-4 font-customFont">
      <button
        @click="handleKeydown"
        class="btn relative"
        type="button"
      >
        <strong>开启二次元 Earthworm</strong>
        <div id="container-stars">
          <div id="stars"></div>
        </div>

        <div id="glow">
          <div class="circle"></div>
          <div class="circle"></div>
        </div>
      </button>
      <a
        href="https://github.com/cuixueshe/earthworm"
        rel="noreferrer noopener"
        target="_blank"
        class="group relative inline-flex h-12 cursor-pointer items-center justify-center overflow-hidden rounded-full px-6 duration-500"
      >
        <div
          class="relative inline-flex -translate-x-0 items-center transition group-hover:-translate-x-6"
        >
          <div
            class="absolute flex translate-x-0 items-center justify-center text-purple-600 opacity-100 transition group-hover:-translate-x-6 group-hover:opacity-0"
          >
            <UIcon
              name="i-ph-star-fill"
              class="h-5 w-5"
            ></UIcon>
          </div>
          <span
            class="bg-gradient-to-r from-purple-600 to-gray-300 bg-clip-text pl-6 font-medium text-transparent"
            >Star us on GitHub</span
          >
          <div
            class="absolute right-0 flex translate-x-12 items-center justify-center text-purple-400 opacity-0 transition group-hover:translate-x-6 group-hover:opacity-100"
          >
            <UIcon
              name="i-ph-arrow-right"
              class="h-5 w-5"
            ></UIcon>
          </div>
        </div>
      </a>
    </div>
    <div class="mt-20 flex w-full justify-center">
      <img
        alt=""
        src="~/assets/home-page-preview.png"
        class="w-4/5 lg:w-3/4"
      />
    </div>

    <CommonDivider />
  </section>
</template>

<script setup lang="ts">
const emit = defineEmits(["start-earthworm"]);

function handleKeydown() {
  emit("start-earthworm");
}
</script>

<style scoped>
.btn {
  display: flex;
  justify-content: center;
  align-items: center;
  width: fit-content;
  overflow: hidden;
  height: 3rem;
  background-size: 300% 300%;
  backdrop-filter: blur(1rem);
  border-radius: 5rem;
  transition: 0.5s;
  animation: gradient_301 5s ease infinite;
  border: double 4px transparent;
  background-image: linear-gradient(#05051d, #05051d),
    linear-gradient(137.48deg, #ffdb3b 10%, #fe53bb 45%, #8f51ea 67%, #0044ff 87%);
  background-origin: border-box;
  background-clip: content-box, border-box;
}

#container-stars {
  position: absolute;
  z-index: -1;
  width: 100%;
  height: 100%;
  overflow: hidden;
  transition: 0.5s;
  backdrop-filter: blur(1rem);
  border-radius: 5rem;
  background-color: #05051d;
}

strong {
  z-index: 2;
  font-family: "Avalors Personal Use";
  font-size: 15px;
  letter-spacing: 5px;
  color: #ffffff;
  /* text-shadow: 0 0 4px white; */
}

#glow {
  position: absolute;
  display: flex;
  width: 12rem;
}

.circle {
  width: 100%;
  height: 30px;
  filter: blur(2rem);
  animation: pulse_3011 4s infinite;
  z-index: -1;
}

.circle:nth-of-type(1) {
  background: rgba(254, 83, 186, 0.636);
}

.circle:nth-of-type(2) {
  background: rgba(142, 81, 234, 0.704);
}

.btn:hover #container-stars {
  z-index: 1;
  background-color: #05051d;
}

.btn:hover {
  transform: scale(1.1);
}

.btn:active {
  border: double 4px #fe53bb;
  background-origin: border-box;
  background-clip: content-box, border-box;
  animation: none;
}

.btn:active .circle {
  background: #fe53bb;
}

#stars {
  position: relative;
  background: transparent;
  width: 200rem;
  height: 200rem;
}

#stars::after {
  content: "";
  position: absolute;
  top: -10rem;
  left: -100rem;
  width: 100%;
  height: 100%;
  animation: animStarRotate 90s linear infinite;
}

#stars::after {
  background-image: radial-gradient(#ffffff 1px, transparent 1%);
  background-size: 50px 50px;
}

#stars::before {
  content: "";
  position: absolute;
  top: 0;
  left: -50%;
  width: 170%;
  height: 500%;
  animation: animStar 60s linear infinite;
}

#stars::before {
  background-image: radial-gradient(#ffffff 1px, transparent 1%);
  background-size: 50px 50px;
  opacity: 0.5;
}

@keyframes animStar {
  from {
    transform: translateY(0);
  }

  to {
    transform: translateY(-135rem);
  }
}

@keyframes animStarRotate {
  from {
    transform: rotate(360deg);
  }

  to {
    transform: rotate(0);
  }
}

@keyframes gradient_301 {
  0% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0% 50%;
  }
}

@keyframes pulse_3011 {
  0% {
    transform: scale(0.75);
    box-shadow: 0 0 0 0 rgba(0, 0, 0, 0.7);
  }

  70% {
    transform: scale(1);
    box-shadow: 0 0 0 10px rgba(0, 0, 0, 0);
  }

  100% {
    transform: scale(0.75);
    box-shadow: 0 0 0 0 rgba(0, 0, 0, 0);
  }
}
</style>
