<script setup lang="ts">
import { RouterView } from 'vue-router'
import PageTransition from '@/components/ui/PageTransition.vue'

// ui components
import Header from '@/components/widgets/Header.vue'
</script>

<template>
  <body class="w-screen h-screen fixed bg-primary">
    <Header />
    <PageTransition>
      <RouterView />
    </PageTransition>
  </body>
</template>
