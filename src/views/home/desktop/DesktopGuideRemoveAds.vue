<script setup lang="ts">
import AppLink from '@/components/AppLink.vue';
import { Icon } from '@iconify/vue/dist/iconify.js';
import ChromiumBrowserIcons from '../_partials/ChromiumBrowserIcons.vue';
</script>
<template>
  <div class="flex">
    <div class="w-1/2">
      <div class="flex justify-center text-[2rem] gap-3">
        <ChromiumBrowserIcons />
      </div>
      <div class="text-center text-gray-500 text-sm mt-3 mb-5">
        And other chromium based browsers...
      </div>
      <div class="mx-5">
        <ul class="list">
          <li>
            Download <b>Ublock Origin Lite</b> extension for your browser
            <AppLink
              target="_blank"
              href="https://chromewebstore.google.com/detail/ublock-origin-lite/ddkjiahejlhfcafbddmgiahcphecmpfh"
            >
              here
            </AppLink>
          </li>
          <li>Click on "Add to [browser]" button. And it must be working now</li>
          <li>
            It must be the <b>Ublock Origin Lite</b> version
            <span
              class="tooltip"
              data-tip="The new Manifest V3 may block the normal Ublock Origin extension from working properly, the Lite version is made to bypass that"
            >
              <Icon
                class="inline text-lg tooltip"
                icon="ph:question-duotone"
              />
            </span>
          </li>
        </ul>
      </div>
    </div>

    <div class="w-1/2">
      <div class="flex justify-center text-[2rem] gap-3 mb-5">
        <Icon icon="logos:firefox" />
      </div>
      <ul class="list">
        <li>
          Download <b>Ublock Origin Lite</b> add-on for Firefox <AppLink
            href="https://addons.mozilla.org/firefox/addon/ublock-origin/"
            target="_blank"
          >
            here
          </AppLink>
        </li>
        <li>Click on "Add to Firefox" button. And it must be working now</li>
      </ul>
    </div>
  </div>
</template>
