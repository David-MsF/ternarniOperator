<script setup>
import { ref } from "vue";

let ukazaneCislo = ref('');
//const spravnyPin = ref('2213');
const poleCisel = [1, 2, 3, 4, 5];

function aktualniCislo(cislo) {
    if (ukazaneCislo.value.length < 4) {
        ukazaneCislo.value += cislo; 
    }    
}

function resetujCislo() {
    ukazaneCislo.value = ''; 
}
/*
function zkontrolujPin() {
    if (ukazaneCislo.value === spravnyPin.value) {
        return true; // PIN je správný
    }
    return false; // PIN není správný
}

function zmenPin(novyPin) {
    spravnyPin.value = novyPin; // Nastaví nový PIN
    resetujCislo(); // Resetuj ukázané číslo
} */
</script>

<template>

    <h2>Naklikej správný Pin (2213)</h2>

    <button @click="aktualniCislo(1)">1</button>
    <button @click="aktualniCislo(2)">2</button>
    <button @click="aktualniCislo(3)">3</button>
    <button @click="aktualniCislo(4)">4</button>
    <button @click="aktualniCislo(5)">5</button>

    <div class="ukazCislo">
        <p>{{ ukazaneCislo }}</p> 
    </div>

    <button @click="resetujCislo()">Reset</button>

    <div class="spravnyKod">
        <p v-if="ukazaneCislo == 2213">Výborně :) Bohužel toto není bankomat.</p>

        <!-- Zkontroluj PIN 
        <p v-else v-if="ukazaneCislo.length > 0">Pin je nesprávný.</p>
        -->
    </div>

    <!-- Tlačítko pro změnu PINu 
    <button @click="zmenPin('1234')">Změnit PIN na 1234</button>
    -->
</template>


<style scoped>
</style>