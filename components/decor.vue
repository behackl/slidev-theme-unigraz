<script setup lang="ts">
const props = defineProps({
    icon: { type: String },
})
</script>

<template>
    <div class="decor text-8xl">
        <slot />
    </div>
</template>