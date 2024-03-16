<template>
    <h1>Hello Vue!</h1>
    <p v-html="'Kurs: <b>' + course.name +'</b>, uczestnicy: ' + course.participants"></p>
    <p v-text="'Kurs: <b>' + course.name +'</b>, uczestnicy: ' + course.participants"></p>
</template>

<script setup>
    import { reactive } from 'vue'
    const course = reactive({ name: 'meme kreatywne', participants: 10 })
</script>