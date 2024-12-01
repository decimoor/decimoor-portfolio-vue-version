<script setup lang="ts">
import { RouterLink } from 'vue-router'
import Nav from '@/components/widgets/Nav.vue'
import MobileNav from '@/components/widgets/MobileNav.vue'

defineOptions({
  name: 'MainHeader',
})
</script>

<template>
  <header class="py-8 xl:py-12 text-white">
    <div class="container mx-auto flex justify-between items-center">
      <RouterLink to="/">
        <h1 class="text-4xl font-semibold relative group">
          decimoor
          <div
            class="absolute left-0 bottom-0 w-[3px] h-[3px] rounded-full bg-accent group-hover:w-full transition-all duration-300"
          ></div>
        </h1>
      </RouterLink>

      <div class="hidden xl:flex gap-8 items-center">
        <Nav />
      </div>

      <div class="xl:hidden">
        <MobileNav />
      </div>
    </div>
  </header>
</template>
