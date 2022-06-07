<template>
  <div class="slidev-layout w-full h-full intro" :style="style">
    <slot />
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
.slidev-layout.intro {
  h1 {
    @apply text-8xl leading-20 font-title font-extrabold;
  }

  h1 + p {
    @apply opacity-90 -mt-4 text-2xl;
  }

  a {
    @apply text-secondary-400 hover:text-secondary-500 dark:(text-white hover:text-gray-200);
  }
}
</style>
