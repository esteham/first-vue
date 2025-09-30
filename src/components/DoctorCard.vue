<script setup lang="ts">
    const props = defineProps({
        doctor: { type: Object, required:true }
    })

    const emit = defineEmits(['book'])

    function bookDoctor()
    {
        emit('book', props.doctor)
    }
</script>

<template>
    <div class="docs-container">
        <img :src="doctor.photo" class="doctor-photo" :alt="doctor.name" />

        <div class="doc-container">
            <h5 class="card-title">{{ doctor.name }}</h5>
            <p>{{ doctor.speciality }}</p>
            <p>{{ doctor.fee }}</p>
            <button class="btn btn-primary" @click="bookDoctor">Book</button>
        </div>
    </div>
</template>
