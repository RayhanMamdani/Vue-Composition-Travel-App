<template>
    <div>
        <h1>Greetings, {{ username }}</h1>
        <button @click="logout">Logout</button>
        <router-link :to="{name:'invoices'}">
        <button>Invoices</button>
        </router-link>
    </div>
</template>

<script setup>  
import { computed } from 'vue';
import { useRouter, useRoute } from 'vue-router'
const username = computed(() => window.user)
const router = useRouter()
const route = useRoute()
const logout = () => {
    window.user = null
    router.push({ name: 'Home' })
}
</script>