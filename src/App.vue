<template>
    <h1>Hello Vue!</h1>
    <p>
        <span>Kurs: {{ course.name }}</span>
        <span v-show="pVisible">, uczestnicy: {{ course.participants }}</span>
    </p>
    <button @click="showParticipant">Uczestnicy</button>
</template>

<script setup>
    import { ref, reactive } from 'vue'
    const course = reactive({ name: 'Programowanie kreatywne', participants: 10 })
    const pVisible = ref(true)
    function showParticipant() {
        pVisible.value = !pVisible.value
    }
</script>