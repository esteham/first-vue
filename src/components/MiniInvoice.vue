<script setup lang="ts">
import { ref, computed } from 'vue'

const qty = ref('')
const price = ref('')
const vat = ref ('')

const total = computed(() => {
  const q = parseFloat(qty.value) || 0
  const p = parseFloat(price.value) || 0
  const v = parseFloat(vat.value) || 0
  return (q * p * (1 + v / 100)).toFixed(2)
})
</script>

<template>
  <div class="mini-invoice">
    <div class="form-group">
      <label for="qty">Qty:</label>
      <input id="qty" type="number" v-model="qty" class="form-input" />
    </div>
    <div class="form-group">
      <label for="price">Price:</label>
      <input id="price" type="number" v-model="price" class="form-input" />
    </div>
    <div class="form-group">
      <label for="vat">VAT (%):</label>
      <input id="vat" type="number" v-model="vat" class="form-input" />
    </div>
    <div class="total-section">
      <h5>Total: {{ total }}</h5>
    </div>
  </div>
</template>

<style scoped>
.mini-invoice {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 20px;
  max-width: 350px;
  background-color: #f9f9f9;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.form-group {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
}

label {
  display: inline-block;
  width: 80px;
  font-weight: bold;
  color: #333;
  margin-right: 10px;
}

.form-input {
  flex: 1;
  padding: 8px 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
  transition: border-color 0.3s ease;
}

.form-input:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 0 2px rgba(0, 123, 255, 0.25);
}

.total-section {
  margin-top: 20px;
  padding-top: 15px;
  border-top: 1px solid #e0e0e0;
  text-align: center;
}

.total-section h5 {
  margin: 0;
  color: #28a745;
  font-size: 18px;
  font-weight: bold;
}
</style>
