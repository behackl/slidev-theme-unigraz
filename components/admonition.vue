<script setup lang="ts">
  import { computed } from 'vue';
  import { Icon } from '@iconify/vue';

  const props = defineProps({
    kind: { type: String, default: "base" },
    title: { type: String },
    icon: { type: String },
  })

  const chosenIcon = computed(() => {
  if (props.icon !== undefined) return props.icon;
  switch (props.kind) {
    case "warning": return "mdi:warning";
    case "danger": return "mdi:alert-octagram";
    case "info": return "mdi:info";
    case "kfu": return "mdi:format-list-bulleted-type";
    default: return "mdi:abacus";
  }
  });
</script>

<template>
  <div class="admonition" :class="'admonition-' + kind">
    <div class="admonition-title">
      <Icon class="admonition-icon" :icon="chosenIcon" />
      {{ title }}
    </div>
    <div class="admonition-body">
      <slot></slot>
    </div>
  </div>
</template>
