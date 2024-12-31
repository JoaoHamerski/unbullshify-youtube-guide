<script setup lang="ts">
import AppAccordion from '@/components/AppAccordion.vue';
import { ref, type Component } from 'vue';

type HomeAccordionsProps = {
  items: Array<{
    title: string
    value: string
    component: Component
  }>
}

defineProps<HomeAccordionsProps>()

const checkedSection = ref('')

</script>

<template>
  <AppAccordion
    v-for="item in items"
    :key="item.title"
    name="desktop-guide-accordion"
    :checked="checkedSection === item.value"
    @change="$event.target.checked === true ? checkedSection = item.value : checkedSection = ''"
  >
    <template #title>
      <h2
        class="flex items-center gap-2 transition-colors"
      >
        <span>{{ item.title }}</span>
      </h2>
    </template>
    <template #body>
      <Component :is="item.component" />
    </template>
  </AppAccordion>
</template>
