<script setup lang="ts">
import { resolveAssetUrl } from '@slidev/client'
import { computed } from 'vue'

const props = defineProps({
  src: { type: String, default: '' },
  type: { type: String, default: '' },
  alt: { type: String, default: '' },
  opacity: { type: [String, Number], default: 1 },
  objectPosition: { type: String, default: 'center' },
  clipRadius: { type: String, default: '81%' },
})

const videoExtensions = ['.mp4', '.webm', '.ogg', '.mov']
const assetUrls = import.meta.glob('/assets/title/*.{avif,gif,jpeg,jpg,mp4,ogg,png,svg,webm}', {
  eager: true,
  query: '?url',
  import: 'default',
}) as Record<string, string>

const resolvedSrc = computed(() => {
  if (!props.src)
    return ''

  const assetKey = props.src.startsWith('/') ? props.src : `/${props.src}`
  return assetUrls[assetKey] ?? resolveAssetUrl(props.src)
})

const isVideo = computed(() => {
  if (props.type)
    return props.type === 'video'

  const src = props.src.toLowerCase().split('?')[0].split('#')[0]
  return videoExtensions.some(extension => src.endsWith(extension))
})
</script>

<template>
  <div
    class="absolute right-0 bottom--20% w-[450px] h-[450px] pointer-events-none"
    style="z-index: -1;"
  >
    <div
      v-if="src"
      class="absolute inset-0 overflow-hidden"
      :style="{ zIndex: 0, clipPath: `circle(${clipRadius} at 100% 100%)` }"
    >
      <video
        v-if="isVideo"
        autoplay
        loop
        muted
        playsinline
        class="w-full h-full object-cover"
        :style="{ opacity, objectPosition }"
      >
        <source :src="resolvedSrc">
      </video>
      <img
        v-else
        :src="resolvedSrc"
        :alt="alt"
        class="w-full h-full object-cover"
        :style="{ opacity, objectPosition }"
      >
    </div>

    <circle-unigraz
      ring-color="#"
      width="450"
      class="absolute inset-0"
      viewBox="0 0 50 50"
      style="z-index: 1;"
    />
  </div>
</template>
