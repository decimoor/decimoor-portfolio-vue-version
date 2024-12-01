<script setup lang="ts">
import { RouterLink, useRoute } from 'vue-router'

const route = useRoute()

type NavItem = {
  name: string
  path: string
}

const navItems: NavItem[] = [
  {
    name: 'Главная',
    link: '/',
  },
  {
    name: 'Навыки',
    link: '/skills',
  },
  {
    name: 'Резюме',
    link: '/resume',
  },
  {
    name: 'Работы',
    link: '/work',
  },
]

// Add component name declaration
defineOptions({
  name: 'MainNav',
})
</script>

<template>
  <nav class="flex gap-8">
    <RouterLink
      v-for="item in navItems"
      :key="item.link"
      :to="item.link"
      :class="[
        'capitalise font-medium hover:text-accent transition-all',
        item.link === route.path ? 'text-accent border-b-2 border-accent' : '',
      ]"
    >
      {{ item.name }}
    </RouterLink>
  </nav>
</template>
