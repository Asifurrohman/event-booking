<template>
    <h1 class="text-4xl font-medium">
        Event Booking App
    </h1>
    <h2 class="text-2xl font-medium">
        All Events
    </h2>
    <section class="grid grid-cols-2 gap-4">
        <EventCard v-for="event in events" :key="event.id" :title="event.title" :date="event.date" :description="event.description" @register="console.log(`You're registered for this event`)" />
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
import axios from 'axios'
import { onMounted, ref } from 'vue'

const events = ref([])

const fetchEvents = async () => {
    try {
        const response = await axios.get('http://localhost:3001/events')
        events.value = response.data
    } catch(error){
        console.error('Error fetching events:', error)
    }
}

onMounted(() => {
    fetchEvents()
})
</script>

<style scoped>

</style>