<script setup lang="ts">
import { ref } from 'vue'
import BookingForm from './BookingForm.vue'
import DoctorCard from './DoctorCard.vue'

interface Doctor {
  id: number
  photo: string
  name: string
  speciality: string
  fee: number
}

interface BookingPayload {
  name: string
  doctor: string
  date: string
}

const selectedDoctor = ref<Doctor | null>(null)

const doctors = ref<Doctor[]>([
  {
    id: 1,
    photo: 'images/mehebuba.jpg',
    name: 'Dr. Mehebuba Ansari',
    speciality: 'Cardiology',
    fee: 1500,
  },
  {
    id: 2,
    photo: 'images/asif.jpg',
    name: 'Dr. Asif Shariar',
    speciality: 'Neurology',
    fee: 1200,
  },
  {
    id: 3,
    photo: 'images/nishi.jpg',
    name: 'Dr. Nishi Gupta',
    speciality: 'Neurology',
    fee: 1400,
  },
])

function handleBook(doctor: Doctor) {
  selectedDoctor.value = doctor
}

function onBooked(payLoad: BookingPayload) {
  alert('Booking done for ' + payLoad.name + ' with ' + payLoad.doctor + ' on ' + payLoad.date)
  selectedDoctor.value = null
}
</script>

<template>
  <h5>Our Specialists</h5>
  <div class="row">
    <div class="col-md-4 mb-3" v-for="doc in doctors" :key="doc.id">
      <DoctorCard :doctor="doc" @book="handleBook" />
    </div>
  </div>

  <hr />

  <div v-if="selectedDoctor">
    <h1>Doctors Details</h1>
    <p>Booking for {{ selectedDoctor.name }}, Speciality: {{ selectedDoctor.speciality }}, Fee: {{ selectedDoctor.fee }}</p>
    <div class="mb-4">
      <BookingForm :prefillDoctor="selectedDoctor.name" @booked="onBooked" ref="apptForm" />
    </div>
  </div>
</template>