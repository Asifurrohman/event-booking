<template>
    <SectionCard>
        <template v-slot:header>
            {{ title }}
        </template>
        {{ date }}
        <template v-slot:footer>
            <div class="space-y-4">
                <p>{{ description }}</p>
                <div class="flex justify-end">
                <RoundButton @click="$emit('register')">
                    Register
                </RoundButton>
            </div>
        </div>
        </template>
    </SectionCard>
</template>

<script setup>
import RoundButton from './RoundButton.vue'
import SectionCard from './SectionCard.vue'

defineProps({
    title: String,
    date: String,
    description: String
})

defineEmits(['register'])
</script>

<style scoped>

</style>