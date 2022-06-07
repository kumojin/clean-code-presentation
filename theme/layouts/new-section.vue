<template>
  <div class="slidev-layout new-section flex justify-center" :style="style">
    <div class="flex flex-col justify-center text-center">
      <slot />
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { handleBackground } from '../layoutHelper'

const props = defineProps({
  image: {
    type: String,
  },
})
const style = computed(() => handleBackground(props.image))
</script>

<style>
.slidev-layout.new-section {
  h1 {
    @apply text-8xl leading-20 mb-0 font-title font-extrabold;
  }

  h1 + p {
    @apply text-2xl mt-4 opacity-100;
  }

  p > img {
    @apply w-2/3 mx-auto;
  }
}
</style>
