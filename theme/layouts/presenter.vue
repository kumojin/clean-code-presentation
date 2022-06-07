<template>
  <div class="bg-main slidev-layout flex flex-col justify-evenly">
    <div class="prose">
      <slot name="title" />
    </div>
    <CornerCurves class="absolute transform bottom-0 right-0 flip-x" />
    <div class="flex items-center">
      <figure class="w-1/3">
        <img
          :src="props.firstPresenterImage"
          class="relative rounded-full object-cover h-40 w-40 border border-8 rounded-border z-10"
        />
      </figure>
      <div class="w-1/3">
        <slot name="first" />
      </div>
    </div>
    <div class="flex items-center">
      <figure class="w-1/3">
        <img
          :src="props.secondPresenterImage"
          class="relative rounded-full object-cover h-40 w-40 border border-8 rounded-border z-10"
        />
      </figure>
      <div class="w-1/3">
        <slot name="second" />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  firstPresenterImage: {
    type: String,
  },
  secondPresenterImage: {
    type: String,
  },
})
</script>
