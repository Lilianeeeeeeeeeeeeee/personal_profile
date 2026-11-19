<script setup lang="ts">
const route = useRoute()
</script>

<template>
  <!-- CSU seal -->
  <NuxtLink to="/" aria-label="Home" class="absolute left-[103px] top-[67px] h-[96px] w-[59px]">
    <img src="/images/seal.png" alt="Caraga State University seal" class="size-full object-cover" />
  </NuxtLink>

  <!-- menu -->
  <NuxtLink to="/" class="absolute left-[1163px] top-[82px] whitespace-nowrap text-[15px] leading-[normal]">
    HOME
  </NuxtLink>
  <NuxtLink to="/profile" class="absolute left-[1259px] top-[82px] whitespace-nowrap text-[15px] leading-[normal]">
    PROFILE
  </NuxtLink>

  <!-- the dot under the current page -->
  <p
    class="absolute top-[72px] whitespace-nowrap text-[40px] leading-[normal]"
    :style="{ left: route.path === '/profile' ? '1284px' : '1180px' }"
  >
    .
  </p>
</template>