<script setup lang="ts">
import EventCard from '@/components/EventCard.vue';
import CategoryCard from '@/components/CategoryCard.vue';
import type { Event } from '@/type';
import { ref } from 'vue';
const events = ref<Event[]>([
  {
    id: 5928101,
    category: 'animal welfare',
    title: 'Cat Adoption Day',
    description: 'Find your new feline friend at this event.',
    location: 'Meow Town',
    date: 'January 28, 2022',
    time: '12:00',
    petsAllowed: true,
    organizer: 'Kat Laydee',
  },
  {
    id: 4582797,
    category: 'food',
    title: 'Community Gardening',
    description: 'Join us as we tend to the community edible plants.',
    location: 'Flora City',
    date: 'Narch 14, 2022',
    time: '10:00',
    petsAllowed: true,
    organizer: 'Fren Pollin',
  },
  {
    id: 8419988,
    category: 'sustainability',
    title: 'Beach Cleanup',
    description: 'Help pick up trash along the shore.',
    location: 'Playa Del Carmen',
    date: 'July 22, 2022',
    time: '11:00',
    petsAllowed: false,
    organizer: 'Catey Wales'
  }
]);
</script>

<template>
  <div class="home">
    <div class="events">
      <div class="event-item" v-for="event in events" :key="event.id">
        <EventCard :event="event"></EventCard>
        <CategoryCard :event="event"></CategoryCard>
      </div>
    </div>
  </div>
</template>


<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.event-item {
  display: flex;
  align-items: center;
}
</style>