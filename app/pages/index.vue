<script setup lang="ts">
useHead({ title: 'Lhyzl Jhyn T. Dooma | Home' })

// every value below is copied from the Figma frame "Desktop - 8" (1440 x 1024)
const stars = [
  { x: 655.72, y: 585.5, w: 40.568, h: 58, r: -19.85 },
  { x: 85, y: 198, w: 51.979, h: 60.29, r: 18.12 },
  { x: 1278, y: 365, w: 23, h: 53, r: 0 },
  { x: 86, y: 918, w: 42.527, h: 58.153, r: 22.6 },
  { x: 357, y: 743, w: 42.527, h: 58.153, r: 22.6 },
  { x: 705.77, y: 293.36, w: 53.934, h: 54.928, r: 43.61 },
  { x: 1369, y: 617, w: 25.318, h: 53.583, r: -1.43 },
  { x: 1353, y: 34, w: 42.527, h: 58.153, r: 22.6 },
]
const dots = [
  { x: 688, y: 161 },
  { x: 1222, y: 693 },
]

// EDIT THE href OF EACH ICON: put your own profile links here
const socials = [
  { name: 'Facebook', src: '/images/facebook.svg', x: 159, inset: '0', href: 'https://www.facebook.com/thisntlilies/' },
  { name: 'Instagram', src: '/images/instagram.svg', x: 218, inset: '0', href: 'https://www.instagram.com/lijijieee' },
  { name: 'X', src: '/images/x.svg', x: 271, inset: '0', href: 'https://x.com/lijijieee' },
  { name: 'Email', src: '/images/google.svg', x: 328, inset: '0 2% 0 0', href: 'mailto:lhyzljhyn.dooma@carsu.edu.ph' },
]
</script>

<template>
  <Stage>
    <!-- circle (fill from Figma + the thin light edge of its glass effect) -->
    <img src="/images/ellipse.svg" alt="" class="absolute left-[676px] top-[216px] h-[666px] w-[660px] max-w-none" />
    <div class="absolute left-[676px] top-[216px] h-[666px] w-[660px] rounded-full border border-white/70" />

    <!-- photo -->
    <img
      src="/images/person.png"
      alt="Portrait of Lhyzl Jhyn T. Dooma"
      class="pointer-events-none absolute left-[624px] top-[-66px] h-[1090px] w-[729px] max-w-none object-cover"
    />

    <Sparkles :stars="stars" :dots="dots" />
    <NavBar />

    <!-- social icons (each one is a link) -->
    <a
      v-for="s in socials"
      :key="s.name"
      :href="s.href"
      :target="s.href.startsWith('http') ? '_blank' : undefined"
      rel="noopener noreferrer"
      :aria-label="s.name"
      class="absolute top-[897px] size-[26px] overflow-clip"
      :style="{ left: `${s.x}px` }"
    >
      <span class="absolute block" :style="{ inset: s.inset }">
        <img :src="s.src" :alt="s.name" class="absolute block size-full max-w-none" />
      </span>
    </a>

    <!-- name -->
    <h1 class="absolute left-[99px] top-[277px] w-[520px] text-[80px] font-semibold leading-[normal]">
      LHYZL JHYN T. DOOMA
    </h1>

    <!-- subtitle -->
    <p class="absolute left-[106px] top-[509px] h-[39px] w-[330px] whitespace-pre-wrap font-sans text-[16px] leading-[normal] text-black/50">
      {{ 'BSIT Student  · Pioneering UI/UX Designer' }}
    </p>

    <!-- introduction -->
    <p class="absolute left-[106px] top-[558px] h-[101px] w-[502px] text-[0px] leading-[0]">
      <span class="text-[17px] leading-[normal]">{{ 'I am an Information Technology student at ' }}</span>
      <span class="text-[17px] font-bold leading-[normal]">Caraga State University</span>
      <span class="text-[17px] leading-[normal]">{{
        ' who enjoys turning ideas into organized, working systems. I like analyzing requirements, designing user-friendly interface, and learning new web technologies. '
      }}</span>
    </p>

    <!-- VIEW PROFILE button -->
    <NuxtLink
      to="/profile"
      class="absolute left-[106px] top-[677px] h-[44px] w-[172px] rounded-[10px] border border-black/15 bg-[#d9d9d9]/60"
    >
      <span class="absolute left-[27px] top-[11px] flex h-[20px] w-[16.041px] items-center justify-center">
        <span class="flex-none rotate-[90.15deg]">
          <span class="relative block h-[15.99px] w-[19.959px]">
            <span class="absolute bottom-1/4 left-[6.7%] right-[6.7%] top-0">
              <img src="/images/play.svg" alt="" class="block size-full max-w-none" />
            </span>
          </span>
        </span>
      </span>
      <span class="absolute left-[34px] top-[11px] h-[24px] w-[112px] whitespace-pre text-right font-sans text-[13px] font-semibold leading-[normal]">
        {{ 'VIEW PROFILE ' }}
      </span>
    </NuxtLink>

    <!-- dashed outline around the photo -->
    <PhotoOutline />
  </Stage>
</template>