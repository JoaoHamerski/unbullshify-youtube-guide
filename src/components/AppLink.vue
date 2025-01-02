<script setup lang="ts">
import { Icon } from '@iconify/vue/dist/iconify.js';

defineProps<{
  target?: string
}>()
</script>

<template>
  <a
    href=""
    class="link-primary"
    :target="target"
    :class="{
      'inline-flex items-center gap-1': target === '_blank'
    }"
  >
    <slot />
    <Icon
      v-if="target === '_blank'"
      icon="ph:arrow-square-out-duotone"
    />
  </a>
</template>
