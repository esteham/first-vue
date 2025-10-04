<script setup lang="ts">
import '@/assets/css/app.css'
</script>

<template>
  <div>
    <Navbar />
    <router-view />
  </div>
</template>

<script lang="ts">
import Navbar from './views/NavbarPage.vue'
export default {
  components: {
    Navbar,
  },
}
</script>

<style scoped>
.app-header {
  background-color: #f8f9fa;
  border-bottom: 1px solid #e9ecef;
  padding: 10px 20px;
}

nav {
  display: flex;
  gap: 10px;
}

button {
  padding: 10px 20px;
  border: 1px solid #007bff;
  background-color: white;
  color: #007bff;
  border-radius: 4px;
  cursor: pointer;
  transition:
    background-color 0.3s,
    color 0.3s;
}

button:hover {
  background-color: #007bff;
  color: white;
}

button.active {
  background-color: #007bff;
  color: white;
}

.app-main {
  padding: 20px;
}
</style>
