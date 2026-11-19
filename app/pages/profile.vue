<script setup lang="ts">
useHead({ title: 'Lhyzl Jhyn T. Dooma | Profile' })

// every value below is copied from the Figma frame "Desktop - 9" (1440 x 1024)
const stars = [
  { x: 1353, y: 34, w: 42.527, h: 58.153, r: 22.6 },
  { x: 323, y: 722, w: 42.527, h: 58.153, r: 22.6 },
  { x: 1278, y: 854, w: 42.527, h: 58.153, r: 22.6 },
  { x: 70, y: 561, w: 42.527, h: 58.153, r: 22.6 },
  { x: 746, y: 371, w: 42.527, h: 58.153, r: 22.6 },
  { x: 1199, y: 243, w: 42.527, h: 58.153, r: 22.6 },
]
const dots = [
  { x: -5, y: 88 },
  { x: 1370, y: 825 },
]

// y of each divider line (x = 70, width = 1300)
const lines = [274, 400, 590, 754, 887]

// pill x, icon x, and where the label sits (right edge or centre)
const hobbies = [
  { name: 'Listening to music', icon: '/images/hobby-music.svg', pill: 535, iconX: 556, labelX: 685, align: '-100%' },
  { name: 'Reading', icon: '/images/hobby-reading.svg', pill: 751, iconX: 796, labelX: 851.5, align: '-50%' },
  { name: 'Playing online games', icon: '/images/hobby-games.svg', pill: 967, iconX: 988, labelX: 1129, align: '-100%' },
  { name: 'Designing', icon: '/images/hobby-designing.svg', pill: 1183, iconX: 1230, labelX: 1315, align: '-100%' },
]
</script>

<template>
  <Stage>
    <Sparkles :stars="stars" :dots="dots" />
    <NavBar />

    <!-- divider lines (black 45%, 0.75px, as in Figma) -->
    <div
      v-for="y in lines"
      :key="y"
      class="absolute left-[70px] h-[0.75px] w-[1300px] bg-black/45"
      :style="{ top: `${y - 0.75}px` }"
    />

    <!-- section labels -->
    <p class="absolute left-[96px] top-[221px] whitespace-nowrap font-sans text-[25px] font-bold leading-[normal] text-black/50">PROFILE</p>
    <p class="absolute left-[96px] top-[326px] whitespace-nowrap font-sans text-[20px] font-bold leading-[normal] text-black/50">PERSONAL</p>
    <p class="absolute left-[96px] top-[479px] whitespace-nowrap font-sans text-[20px] font-bold leading-[normal] text-black/50">EDUCATION</p>
    <p class="absolute left-[96px] top-[659px] whitespace-nowrap font-sans text-[20px] font-bold leading-[normal] text-black/50">SKILLS &amp; INTERESTS</p>
    <p class="absolute left-[96px] top-[802px] whitespace-nowrap font-sans text-[20px] font-bold leading-[normal] text-black/50">HOBBIES</p>

    <!-- greeting and round photo -->
    <div class="absolute left-[1229px] top-[167px] h-[101px] w-[232px] -translate-x-full text-right text-[0px] leading-[0]">
      <p class="text-[18px] leading-[normal] text-black/50">Good day,</p>
      <p class="text-[18px] leading-[normal]">I am Lhyzl Jhyn T. Dooma</p>
    </div>

    <!-- avatar: ring + shadow from Figma, photo with the Figma crop, light glass edge on top -->
    <div class="absolute left-[1255px] top-[128px] h-[116px] w-[115px]">
      <div class="absolute inset-[0_-3.48%_-6.9%_-3.48%]">
        <img src="/images/avatar-ring.svg" alt="" class="block size-full max-w-none" />
      </div>
    </div>
    <div class="absolute left-[1255px] top-[129px] size-[115px] overflow-hidden rounded-full">
      <img
        src="/images/avatar.png"
        alt="Lhyzl Jhyn T. Dooma"
        class="pointer-events-none absolute left-[0.43%] top-[-20.99%] h-[149.98%] w-full max-w-none"
      />
    </div>
    <div class="pointer-events-none absolute left-[1255px] top-[129px] size-[115px] rounded-full border-[1.5px] border-white/80" />

    <!-- PERSONAL -->
    <div class="absolute left-[1353px] top-[304px] h-[62px] w-[590px] -translate-x-full text-right font-sans text-[16px] text-black/50">
      <p class="font-bold leading-[normal]">Lhyzl Jhyn T. Dooma</p>
      <p class="leading-[normal]">22 years old · San Vicente, Butuan City, Agusan Del Norte, Philippines</p>
      <p class="leading-[normal]">lhyzljhyn.dooma@carsu.edu.ph</p>
    </div>

    <!-- EDUCATION -->
    <div class="absolute left-[1370px] top-[428px] h-[131px] w-[590px] -translate-x-full whitespace-pre-wrap text-right font-sans text-[16px] text-black/50">
      <p class="font-bold leading-[normal]">Caraga State University</p>
      <p class="leading-[normal]">BS Information Technology - 2024-Present</p>
      <p class="h-6" />
      <p class="font-bold leading-[normal]">San Vicente National High School</p>
      <p class="leading-[normal]">Junior High- Senior High - 2017-2024</p>
    </div>

    <!-- SKILLS & INTERESTS -->
    <div class="absolute left-[1365px] top-[608px] h-[131px] w-[590px] -translate-x-full whitespace-pre-wrap text-right font-sans text-[16px] font-bold leading-[0] text-black/50">
      <p>
        <span class="leading-[normal]">{{ 'SKILLS            ' }}</span>
        <span class="font-normal leading-[normal]">{{ ' UI/UX Design   ·  HTML & CSS   ·  Business Analysis   · SQL   ·  JavaScript   ·  Vue/Nuxt   ·' }}</span>
      </p>
      <p>
        <span class="leading-[normal]">{{ 'INTERESTS   ' }}</span>
        <span class="font-normal leading-[normal]">{{ 'Web design   ·  Database   ·  Computer Vision   ·  Machine Learning   ·  Robotics   ·  Data Analytics   ·  Computer Sciences   ·  Web Development  ' }}</span>
      </p>
    </div>

    <!-- HOBBIES -->
    <template v-for="h in hobbies" :key="h.name">
      <div
        class="absolute top-[791px] h-[51px] w-[182px] rounded-[10px] bg-white/50"
        :style="{ left: `${h.pill}px` }"
      />
      <img :src="h.icon" alt="" class="absolute top-[805px] size-[24px]" :style="{ left: `${h.iconX}px` }" />
      <p
        class="absolute top-[810px] whitespace-nowrap font-sans text-[10px] font-bold leading-[normal] text-black/80"
        :style="{ left: `${h.labelX}px`, transform: `translateX(${h.align})` }"
      >
        {{ h.name }}
      </p>
    </template>

    <!-- Back to HOME -->
    <NuxtLink
      to="/"
      class="absolute left-[629px] top-[924px] h-[51px] w-[182px] rounded-[10px] bg-white/50"
    >
      <span class="absolute left-[137px] top-[16px] -translate-x-full whitespace-nowrap text-right font-sans text-[13px] font-bold leading-[normal] text-black/80">
        Back to HOME
      </span>
    </NuxtLink>
  </Stage>
</template>