<template>
  <div class="bg-main slidev-layout">
    <div class="grid grid-cols-2 gap-8" :class="{ 'gap-16': $attrs.reverse }">
      <div
        class="prose pr-16"
        :class="{ 'order-1 text-right': $attrs.reverse }"
      >
        <slot name="default" />
      </div>
      <figure class="relative flex flex-col justify-center">
        <img
          :src="mediaUrl"
          class="rounded-lg shadow-lg object-cover z-10"
        />
        <figcaption class="mt-2 text-xs w-full">
          {{ props.caption }}
        </figcaption>
      </figure>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { resolveAssetUrl } from '../layoutHelper'

const props = defineProps({
  media: {
    type: String,
  },
  caption: {
    type: String,
  },
})

const mediaUrl = computed(() => resolveAssetUrl(props.media))

</script>
