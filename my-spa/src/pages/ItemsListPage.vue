<script setup>
import { ref, onMounted } from 'vue'

const items = ref([])

onMounted(async () => {
  const res = await fetch('/data.json')
  items.value = await res.json()
})
</script>

<template>
  <div>
    <h1>Items</h1>

    <ul>
      <li v-for="item in items" :key="item.id">
        <router-link :to="`/items/${item.id}`">
          {{ item.title }}
        </router-link>
      </li>
    </ul>
  </div>
</template>
