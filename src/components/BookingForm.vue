<!-- eslint-disable @typescript-eslint/no-unused-vars -->
<script setup lang="ts">
import { reactive, computed, watch } from 'vue'

const props = defineProps({
  prefillDoctor: {
    type: String,
    default: '',
  },
})

const emit = defineEmits(['booked'])
const form = reactive({
  name: '',
  phone: '',
  doctor: '',
  date: '',
  notes: '',
})

const errors = reactive({
  name: '',
  phone: '',
  doctor: '',
  date: '',
})

watch(
  () => props.prefillDoctor,
  (nv) => {
    form.doctor = nv
  },
)

function validate() {
  errors.name = form.name.trim() ? '' : 'Name is required'
  errors.phone = /^\d{10,14}$/.test(form.phone) ? '' : 'Valid phone number is required'
  errors.doctor = form.doctor ? '' : 'Please select a doctor'
  errors.date = form.date ? '' : 'Please select a date'

  return !errors.name && !errors.phone && !errors.doctor && !errors.date
}

function submit() {
  if (validate()) {
    emit('booked', { ...form })
    form.name = ''
    form.phone = ''
    form.doctor = ''
    form.date = ''
    form.notes = ''
  }
}
</script>

<template>
  <div class="booking-form">
    <h2>Book an Appointment</h2>
    <form @submit.prevent="submit">
      <div class="form-group">
        <label for="name">Name:</label>
        <input v-model="form.name" id="name" type="text" />
        <span class="error" v-if="errors.name">{{ errors.name }}</span>
      </div>
      <div class="form-group">
        <label for="phone">Phone Number:</label>
        <input v-model="form.phone" id="phone" type="text" />
        <span class="error" v-if="errors.phone">{{ errors.phone }}</span>
      </div>
      <div class="form-group">
        <label for="doctor">Select Doctor:</label>
        <input v-model="form.doctor" id="doctor" type="text" />
        <span class="error" v-if="errors.doctor">{{ errors.doctor }}</span>
      </div>
      <div class="form-group">
        <label for="date">Select Date:</label>
        <input v-model="form.date" id="date" type="date" />
        <span class="error" v-if="errors.date">{{ errors.date }}</span>
      </div>
      <div class="form-group">
        <label for="notes">Additional Notes:</label>
        <textarea v-model="form.notes" id="notes"></textarea>
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>
<style scoped>
.booking-form {
  max-width: 500px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

h2 {
  text-align: center;
  color: #333;
  margin-bottom: 20px;
  font-size: 24px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
  color: #555;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 16px;
  box-sizing: border-box;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
}

textarea {
  resize: vertical;
  min-height: 80px;
}

.error {
  color: #dc3545;
  font-size: 14px;
  margin-top: 5px;
  display: block;
}

.btn {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  text-align: center;
  text-decoration: none;
  transition: background-color 0.3s ease;
}

.btn-primary {
  background-color: #007bff;
  color: white;
  width: 100%;
}

.btn-primary:hover {
  background-color: #0056b3;
}

.btn:disabled {
  background-color: #6c757d;
  cursor: not-allowed;
}
</style>