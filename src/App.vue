<template>
    <h1>Hello Vue!</h1>
    <table>
        <tr v-for="c, index in courses" :key="c.id">
            <td>{{ index + 1 }}.</td>
            <td>Kurs: {{ c.name }}</td>
            <td>Uczestnicy: {{ c.participants }}</td>
        </tr>
    </table>
    <p><button @click="courses.reverse()">Odwróć</button></p>
    <p><button @click="courses = courses.filter(c => c.exam)">Z egzaminem</button></p>

</template>

<script setup>
    import courses from './data.js'
</script>   