<script setup lang="ts">
import { ref } from 'vue'
import '@/assets/css/app.css'

const patientname = ref('')
const visits = ref(0)
const booked = ref(false)

const doctors = [
  {
    id: 1,
    photo: 'images/mehebuba.jpg',
    name: 'Dr. Mehebuba Ansari',
    speciality: 'Cardiology',
  },
  {
    id: 2,
    photo: 'images/asif.jpg',
    name: 'Dr. Asif Shariar',
    speciality: 'Neurology',
  },
  {
    id: 2,
    photo: 'images/nishi.jpg',
    name: 'Dr. Nishi Gupta',
    speciality: 'Neurology',
  },
]

function confirmBooking() {
  booked.value = true
  visits.value++
}
</script>

<template>
  <div class="docs-container">
    <div v-for="doc in doctors" :key="doc.id" class="doc-container">
      <img :src="doc.photo" alt="doctor photo" class="doctor-photo" />
      <h3>Name: {{ doc.name }}</h3>
      <p>Speciality: {{ doc.speciality }}</p>
    </div>
  </div>

  <div class="form-container">
    <div>
      <label for="name" class="form-label">Name :</label>
      <input id="name" v-model="patientname" class="form-input" placeholder="Enter patient name" />
      <p class="welcome-msg" v-if="patientname">
        Welcome, <span>{{ patientname }}</span>
      </p>
    </div>

    <div>
      <p>Total Visit: {{ visits }}</p>
      <button @click="confirmBooking">Confirm Booking</button>
      <p v-if="booked">Booking Successfully</p>
      <p v-else>No Booking Yet</p>
    </div>
  </div>
</template>

<style scoped></style>
