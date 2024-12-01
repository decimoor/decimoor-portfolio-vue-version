<script setup lang="ts">
import { RouterLink, useRoute } from 'vue-router'

const route = useRoute()

import { Sheet, SheetContent, SheetTrigger, SheetClose } from '../ui/sheet'

import { Menu } from '@vicons/carbon'

type NavItem = {
  name: string
  path: string
}

const navItems: NavItem[] = [
  { name: 'Главная', path: '/' },
  { name: 'Контакты', path: '/contact' },
  { name: 'Резюме', path: '/resume' },
  { name: 'Работы', path: '/works' },
  { name: 'Скилы', path: '/skills' },
]
</script>

<template>
  <Sheet>
    <SheetTrigger class="flex justify-center items-center">
      <Menu class="text-[32px] text-white hover:text-accent transition-colors duration-300 w-9" />
    </SheetTrigger>
    <SheetContent class="flex flex-col bg-primary">
      <div class="mt-32 mb-40 text-center text-2xl flex items-center justify-center">
        <SheetClose :as-child="true">
          <RouterLink to="/" class="w-fit">
            <h1 class="text-4xl font-semibold relative group w-fit">
              decimoor
              <div
                class="absolute left-0 bottom-0 w-[3px] h-[3px] bg-accent group-hover:w-full transition-all duration-300"
              ></div>
            </h1>
          </RouterLink>
        </SheetClose>
      </div>

      <nav class="flex flex-col justify-center items-center gap-8">
        <SheetClose :as-child="true" v-for="item in navItems" :key="item.path">
          <RouterLink
            :to="item.path"
            :class="`${item.path === route.path && 'text-accent border-b-2 border-accent'} text-xl capitalize hover:text-accent transition-all`"
          >
            {{ item.name }}
          </RouterLink>
        </SheetClose>
      </nav>
    </SheetContent>
  </Sheet>
</template>
