<script setup lang="ts">
import { useRoute } from 'vue-router'

const route = useRoute()
</script>

<template>
  <div :key="route.path">
    <div
      v-motion
      :initial="{ opacity: 0, y: 20 }"
      :enter="{ opacity: 1, y: 0 }"
      :leave="{ opacity: 0, y: -20 }"
      :transition="{ duration: 300 }"
    >
      <slot></slot>
    </div>
  </div>
</template>
