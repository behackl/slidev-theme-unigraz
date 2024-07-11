<script setup lang="ts">
const props = defineProps({
    title: { type: String },
})
</script>

<template>
    <div class="block">
    <span class="block-title">{{ title }}</span>
        <slot></slot>
    </div>
</template>