<script setup lang="ts">
const props = defineProps({
  presenterName: { type: String },
  affiliation: { type: String },
  extra: { type: String },
  coverMedia: { type: String, default: '' },
  coverMediaType: { type: String, default: '' },
  coverMediaAlt: { type: String, default: '' },
  coverMediaOpacity: { type: [String, Number], default: 1 },
  coverMediaPosition: { type: String, default: 'center' },
  coverMediaClipRadius: { type: String, default: '81%' },
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
      <cover-circle-media
        :src="coverMedia"
        :type="coverMediaType"
        :alt="coverMediaAlt"
        :opacity="coverMediaOpacity"
        :object-position="coverMediaPosition"
        :clip-radius="coverMediaClipRadius"
      >
        <template v-if="$slots.circle" #default>
          <slot name="circle" />
        </template>
      </cover-circle-media>
    </div>
  </div>
</template>
