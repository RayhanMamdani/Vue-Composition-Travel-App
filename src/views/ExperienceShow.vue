<template>
    <section>
        <h1>{{ experience.name }}</h1>
        <img :src="`/images/${experience.image}`" alt="">
        <p>{{ experience.description }}</p>
    </section>
</template>

<script setup>
import sourceData from '../data.json'
import { computed } from 'vue';
const props = defineProps({
    id: { type: Number, required: true },
    experienceSlug: { type: String, required: true }
})
const description = computed(() => {
    return sourceData.destinations.find(destination => destination.id === props.id)
})
const experience = computed(() => {
    return description.value.experiences.find(experience => experience.slug === props.experienceSlug)
})
</script>