<template>
  <div class="bg-main slidev-layout">
    <div class="grid grid-cols-2 gap-8">
      <div
        class="prose pr-16"
      >
        <slot name="default" />
      </div>
      <div
        class="prose pr-16"
      >
        <slot name="right" />
      </div>
    </div>
  </div>
</template>
