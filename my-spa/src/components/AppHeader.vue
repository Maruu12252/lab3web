<template>
  <header>
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/items">Items</router-link>
    </nav>
  </header>
</template>

<style scoped>
header {
  padding: 16px;
  background: #eee;
}
nav a {
  margin-right: 10px;
}
</style>
