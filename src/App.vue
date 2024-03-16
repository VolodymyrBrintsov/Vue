<template>
    <h1>Hello Vue!</h1>
    <h2>Typy proste - ref</h2>
    <p>Kurs: {{ courseName }}, uczestnicy: {{ courseParticipants }}</p>
    <h2>Obiekty - reactive</h2>
    <p>Kurs: {{  course.name }}, uczestnicy: {{ course.participants }}</p>
</template>

<script setup>
    import { ref, reactive } from 'vue'
    const courseName = ref('Bogate aplikacje internetowe')
    const courseParticipants = ref(20)
    const course = reactive({
         name: 'Programowanie kreatywne',
         participants: 10
    })
    courseParticipants.value++
    course.participants++
</script> vue