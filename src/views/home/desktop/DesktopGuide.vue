<script setup lang="ts">
import { Icon } from '@iconify/vue'
import AppCard from '@/components/AppCard.vue'
import DesktopGuideRemoveAds from './DesktopGuideRemoveAds.vue'
import DesktopGuideSkipSponsor from './DesktopGuideSkipSponsor.vue'
import HomeAccordions from '../HomeAccordions.vue';

const DESKTOP_GUIDE_ITEMS = [
  {
    title: 'Remove basic ads',
    value: 'remove-basic-ads',
    component: DesktopGuideRemoveAds
  },
  {
    title: 'Automatically skip in-video sponsors',
    value: 'skip-sponsors',
    component: DesktopGuideSkipSponsor
  },
  {
    title: 'Remove click bait thumbnails',
    value: 'click-bait-thumbnails',
    component: DesktopGuideSkipSponsor
  },
  {
    title: 'Return dislike button',
    value: 'click-bait-thumbnails',
    component: DesktopGuideSkipSponsor
  }
]

</script>

<template>
  <div class="w-[65%] mx-auto">
    <AppCard>
      <div class="flex justify-center mb-10">
        <Icon
          icon="ph:monitor-duotone"
          class="text-[#ff0033] text-[6rem]"
        />
      </div>

      <div class="flex flex-col gap-5">
        <HomeAccordions :items="DESKTOP_GUIDE_ITEMS" />
      </div>
    </AppCard>
  </div>
</template>
