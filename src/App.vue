<template>
    <h1>Hello Vue!</h1>
    <p>Kurs: {{ course.name }}, uczestnicy: {{ course.participants }}</p>
    <p>Zmień nazwę kursu:</p>
    <input size="50" v-model="course.name">
</template>

<script setup>
    import { reactive } from 'vue'
    const course = reactive({ name: 'Programowanie kreatywne', participants: 10 })
    function onInput(e) {
        course.name = e.target.value
    }
</script>