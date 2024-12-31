<script setup lang="ts">
import { Icon } from '@iconify/vue/dist/iconify.js';

type AppAccordionProps = {
  name: string
  checked?: boolean
}

defineEmits(['change'])

withDefaults(
  defineProps<AppAccordionProps>(), {
    checked: false
  }
)

</script>

<template>
  <div class="collapse bg-base-200 rounded-none">
    <input
      :checked="checked"
      type="checkbox"
      :name="name"
      class="peer"
      @change="$emit('change', $event)"
    >
    <div class="peer-hover:bg-[#ff0033]/60 peer-checked:bg-[#ff0033]/70  peer-hover:text-white collapse-title text-xl font-bold text-left ">
      <div
        class="flex items-center transition-all gap-2"
        :class="{
          'text-white': checked
        }"
      >
        <Icon
          icon="ph:caret-right-duotone"
          class="transition-all"
          :class="{
            'rotate-90 text-white': checked,
            'rotate-0': !checked,
          }"
        />
        <slot
          name="title"
          v-bind="{ checked }"
        />
      </div>
    </div>
    <div class="collapse-content">
      <slot
        name="body"
        v-bind="{ checked }"
      />
    </div>
  </div>
</template>
