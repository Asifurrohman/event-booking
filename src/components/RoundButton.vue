<template>
    <button @click="$emit('click')" :class="['text-sm font-medium rounded-full px-3 py-1 cursor-pointer', variants[variant] ?? variants.default]">
        <slot></slot>
    </button>
</template>

<script setup>
defineProps({
    variant: {
        type: String,
        default: 'default'
    }
})

defineEmits(['click'])

const variants = {
    default: 'border border-gray-200 hover:bg-gray-100',
    danger: 'bg-red-200 enabled:hover:bg-red-300 text-red-900'
}
</script>

<style scoped>

</style>