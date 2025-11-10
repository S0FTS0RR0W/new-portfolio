<template>
  <nav class="navbar">
    <div class="container">
      <NuxtLink to="/" class="brand">Charlie Brown</NuxtLink>
      <div class="nav-links">
        <NuxtLink to="/" class="nav-link">Home</NuxtLink>
        <NuxtLink to="/blog" class="nav-link">Blog</NuxtLink>
        <button @click="toggleTheme">
          {{ colorMode.preference === 'dark' ? 'Light' : 'Dark' }}
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const colorMode = useColorMode()

const toggleTheme = () => {
  colorMode.preference = colorMode.preference === 'dark' ? 'light' : 'dark'
}
</script>

<style scoped>
.navbar {
  background: var(--background-color);
  border-bottom: 1px solid var(--border-color);
  padding: 14px 0;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.container {
  max-width: 980px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
}

.brand {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--text-color);
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 20px;
  align-items: center;
}

.nav-link {
  color: var(--text-color);
  text-decoration: none;
  font-weight: 600;
}

.nav-link:hover {
  color: #0ea5a4;
}

button {
  background: var(--background-color);
  color: var(--text-color);
  border: 1px solid var(--text-color);
  padding: 5px 10px;
  cursor: pointer;
  border-radius: 5px;
}
</style>
