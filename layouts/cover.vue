<script setup lang="ts">
const props = defineProps({
  presenterName: { type: String },
  affiliation: { type: String },
  extra: { type: String },
})
</script>

<template>
  <div class="slidev-layout cover">
    <div class="my-auto w-full">
      <slot />

      <h4 class="mt-8">{{ presenterName }}</h4>
      <div class="opacity-50" style="font-size: 15px;">
        {{ affiliation }}
      </div>
      <div class="mt-8" style="font-size: 15px;">
        <slot name="extra">{{ extra }}</slot>
      </div>
    </div>
  </div>
</template>
