<script setup lang="ts">
const outer = ref<HTMLElement | null>(null)
const scale = ref(1)
let observer: ResizeObserver | undefined

onMounted(() => {
  const update = () => {
    if (outer.value) scale.value = outer.value.clientWidth / 1440
  }
  update()
  observer = new ResizeObserver(update)
  if (outer.value) observer.observe(outer.value)
})

onBeforeUnmount(() => observer?.disconnect())
</script>

<template>
  <!-- the outer box takes the width of the window -->
  <div ref="outer" class="relative w-full overflow-hidden" :style="{ height: `${1024 * scale}px` }">
    <!-- the inner box is your Figma frame (1440 x 1024), zoomed to fit -->
    <div class="relative h-[1024px] w-[1440px]" :style="{ zoom: String(scale) }">
      <slot />
    </div>
  </div>
</template>