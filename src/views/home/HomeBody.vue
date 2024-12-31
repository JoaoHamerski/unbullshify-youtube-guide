<script setup lang="ts">
import DesktopGuide from './desktop/DesktopGuide.vue'
import MobileGuide from './mobile/MobileGuide.vue'
import { TabGroup, TabList, Tab, TabPanel, TabPanels } from '@headlessui/vue'
import { Icon } from '@iconify/vue/dist/iconify.js'

const TABS = [
  { label: 'Desktop', icon: 'ph:monitor-duotone', component: DesktopGuide },
  { label: 'Phone', icon: 'ph:device-mobile-duotone', component: MobileGuide },
]
</script>

<template>
  <div class="w-full mx-10 text-center">
    <TabGroup>
      <TabList
        v-slot="{ selectedIndex }"
        class="inline-flex gap-1 bg-base-300 rounded-lg overflow-hidden p-1 mb-10"
      >
        <Tab
          v-for="(tab, index) in TABS"
          :key="tab.label"
          class="px-6 py-2 rounded-lg transition-colors flex items-center gap-2 font-bold focus:outline focus:outline-[2px] focus:outline-[#ff0033]/60 border-2 border-base-300"
          :class="{
            'bg-white/85 text-[#ff0033] font-bold': selectedIndex === index,
            'hover:bg-white/10': selectedIndex !== index,
          }"
          as="button"
        >
          <Icon :icon="tab.icon" />
          {{ tab.label }}
        </Tab>
      </TabList>

      <TabPanels>
        <TabPanel
          v-for="tab in TABS"
          :key="tab.label"
        >
          <Component :is="tab.component" />
        </TabPanel>
      </TabPanels>
    </TabGroup>
  </div>
</template>
