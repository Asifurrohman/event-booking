<template>
    <h1 class="text-4xl font-medium">
        Event Booking App
    </h1>
    <h2 class="text-2xl font-medium">
        All Events
    </h2>
    <section class="grid grid-cols-2 gap-4">
        <EventCard v-for="i in 8" :key="i.id" title="Konferensi Meja Bundar" date="2026-06-01" description="Konferensi tentang vue dan JS" @register="console.log(`You're registered for this event`)" />
    </section>
    <h2 class="text-2xl font-medium">
        Your Bookings
    </h2>
    <section class="grid grid-cols-1 gap-2">
        <BookingItem v-for="i in 3" :key="i"></BookingItem>
    </section>
</template>

<script setup>
import BookingItem from '@/components/BookingItem.vue'
import EventCard from '@/components/EventCard.vue'
</script>

<style scoped>

</style>