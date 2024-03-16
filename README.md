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