<template>
    <h1>Hello Vue!</h1>
    <p :class="courseClass">
        Kurs: {{ course.name }}, uczestnicy: {{ course.participants }}
    </p>
</template>

<script setup>
    import { ref, reactive } from 'vue'
    const course = reactive({ name: 'Programowanie kreatywne', participants: 10 })
    const courseClass = ref('b')
</script>

<style scoped>
    .c1 { color: rgb(0, 255, 4) }
    .c2 { color: red }
    .b  { font-weight: 700 }
</style>