# Vue 3 + Vite

Pusta aplikacja Vue 3 + Vite.

## Zalecana konfiguracja IDE

[Visual Studio Code](https://code.visualstudio.com/) + [Vue - Official](https://marketplace.visualstudio.com/items?itemName=Vue.volar).

## Konfiguracja Vite

- Skonfigurowana obsługa HTTPS.
- Skonfigurowana obsługa aliasu **@** - mapuje folder **src** aplikacji, co pozwala na prostsze ścieżki przy imporcie.

## Zmiene:
w js
1. Proste
2. objekty

w vue
1. `reactive` - object (objekt obwijający inny objekt)
2. `ref` - zmienna prosta

## v-bind
To dyrektywa wiążąca atrybut HTML z kodem javascript i zmiennymi reaktywnymi (nie można używać podwójnych wąsów wewnątrz znaczników HTML). Co ważne dla atrybutu class można mieszać w jednym znaczniku odwołania statyczne i dynamiczne. Zostaną one w prawidłowy sposób połączone

**`const courseClass = ref('c1')`**

**`<p :class="courseClass"> Kurs: {{ course.name }}, uczestnicy: {{ course.participants }}</p>`**

## v-on

Kod javascript może reagować na zdarzenia w dokumencie przez zdefiniowanie event listeners dla poszczególnych znaczników. Typowym przykładem będzie nasłuchiwanie zdarzenia click na przycisku.

Vue definiuje obsługę zdarzeń dyrektywą v-on. Do ostatniego przykładu możemy pod znacznikiem p dodać przycisk, którego kliknięcie będzie zmieniało kolor akapitu:

`<button v-on:click="courseClass = courseClass == 'c1' ? 'c2' : 'c1'">Kolor</button>`

## v-model
Ta dyrektywa to skrót łączący v-bind i v-on w celu stworzenia dwukierunkowego wiązania między elementem dokumentu, a zmienną reaktywną.

W ostatnim przykładzie usuwamy style i przycisk do zmiany koloru. Zamiast tego wprowadzamy element` <input>` i opisujący go akapit. Aby wartością dla input stała się nasza nazwa kursu wiążemy go przy pomocy v-bind z course.name.

Wiązanie v-bind działa w jedną stronę i nie spowoduje aktualizacji nazwy kursu w akapicie powyżej po zmianie tekstu w kontrolce. Aby tak się stało trzeba nasłuchiwać i reagować na zmiany w input. Realizujemy to dyrektywą v-on dla zdarzenia input. Definiujemy funkcję, która po zmianie wartości w kontrolce input zmienia wartość pola name zmiennej reaktywnej course.

`function onInput(e) {
    course.name = e.target.value
}`

**`<p>Kurs: {{ course.name }}, uczestnicy: {{ course.participants }}</p>
    <p>Zmień nazwę kursu:</p>
    <input size="50" :value="course.name" @input="onInput">`**

### or
**`<input size="50" v-model="course.name">`**

## v-if i v-show
Te dyrektywy pozwalają pokazywać warunkowo elementy dokumentu.

Chcemy stworzyć przycisk do pokazywania/ukrywania liczby uczestników kursu - jego kliknięcie będzie przełączało wartość zmiennej pVisible między true i false. W akapicie wyróżnimy dwa elementy span jeden na nawę kursu i drugi na uczestników. 

**`<span v-show="pVisible">, uczestnicy: {{ course.participants }}</span>`**
- renderuje wszystkie spany

### or

**`<span v-if="pVisible">, uczestnicy: {{ course.participants }}</span>
    <span v-else>, liczba uczestników ukryta.</span>`**

- usuwa spany

## v-for
Dość często zachodzi potrzeba wyrenderowania listy podobnych elementów różniących się danymi. Pomaga w tym dyrektywa v-for.

**\<template>\
&emsp; \<h1>Hello Vue!</h1>\
&emsp; \<template v-for="c, index in courses" :key="c.id">\
&emsp; &emsp; \<p>{{ index + 1 }}.</p>
&emsp; &emsp; \<p>Kurs: {{ c.name }}</p>
&emsp; &emsp; \<p>Uczestnicy: {{ c.participants }}</p>
&emsp; \</template>\
\</template>**

### responsywność tablic:
1. `<p><button @click="courses.reverse()">Odwróć</button></p>`
2. `<p><button @click="courses = courses.filter(c => c.exam)">Z egzaminem</button></p>`