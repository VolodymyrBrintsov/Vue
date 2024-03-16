<template>
    <h1>Hello Vue!</h1>
    <p :class="courseClass">
        Kurs: {{ course.name }}, uczestnicy: {{ course.participants }}
    </p>
    <button @click="changeColor">Kolor</button>
</template>

<script setup>
    import { ref, reactive } from 'vue'
    const course = reactive({ name: 'Programowanie kreatywne', participants: 10 })
    const courseClass = ref('c1')
    function changeColor() {
        courseClass.value = courseClass.value == 'c1' ? 'c2' : 'c1'
    }
</script>

<style scoped>
    .c1 { color: blue }
    .c2 { color: red }
</style>