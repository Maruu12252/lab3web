<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const item = ref(null)

onMounted(async () => {
  const res = await fetch('/data.json')
  const all = await res.json()
  item.value = all.find(i => i.id === Number(route.params.id))
})
</script>

<template>
  <div v-if="item">
    <h1>{{ item.title }}</h1>
    <p>{{ item.text }}</p>
    <router-link to="/items">← Back to Items</router-link>

  </div>

  <p v-else>Loading...</p>
</template>
