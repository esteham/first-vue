<script setup lang="ts">
import { ref } from 'vue'
import '@/assets/css/app.css'
import Doctor from './components/Doctor.vue'
import MiniInvoice from './components/MiniInvoice.vue'

const activeComponent = ref('doctor')
</script>

<template>
  <header class="app-header">
    <nav>
      <button
        @click="activeComponent = 'doctor'"
        :class="{ active: activeComponent === 'doctor' }"
      >
        Doctor
      </button>
      <button
        @click="activeComponent = 'invoice'"
        :class="{ active: activeComponent === 'invoice' }"
      >
        Mini Invoice
      </button>
    </nav>
  </header>

  <main class="app-main">
    <Doctor v-if="activeComponent === 'doctor'" />
    <MiniInvoice v-if="activeComponent === 'invoice'" />
  </main>
</template>

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
  transition: background-color 0.3s, color 0.3s;
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
