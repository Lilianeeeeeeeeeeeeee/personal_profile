<script setup lang="ts">
defineProps<{
  stars?: { x: number; y: number; w: number; h: number; r: number }[]
  dots?: { x: number; y: number }[]
}>()
</script>

<template>
  <!-- the "+" marks: a box at the Figma position, with the "+" rotated inside -->
  <div
    v-for="(s, i) in stars"
    :key="'star' + i"
    class="absolute flex items-center justify-center"
    :style="{ left: `${s.x}px`, top: `${s.y}px`, width: `${s.w}px`, height: `${s.h}px` }"
  >
    <div class="flex-none" :style="{ transform: `rotate(${s.r}deg)` }">
      <p class="whitespace-nowrap text-[40px] leading-[normal]">+</p>
    </div>
  </div>

  <!-- the blurred "..." -->
  <p
    v-for="(d, i) in dots"
    :key="'dot' + i"
    class="absolute whitespace-nowrap text-[100px] font-semibold leading-[normal] blur-[2px]"
    :style="{ left: `${d.x}px`, top: `${d.y}px` }"
  >
    ...
  </p>
</template>