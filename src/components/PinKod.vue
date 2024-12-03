<script setup>
import { ref } from "vue";
import gShort from "../assets/sound/g.wav";
import fShort from "../assets/sound/f.wav";


let ukazaneCislo = ref('');
const spravnyPin = ref('2213');
const poleCisel = [1, 2, 3, 4, 5];

function aktualniCislo(cislo) {
    if (ukazaneCislo.value.length < 4) {
        ukazaneCislo.value += cislo;
    }
}


/*
function zmenPin(novyPin) {
    spravnyPin.value = novyPin;     
} */
const zvukGecko = new Audio(gShort);
const zvukEfko = new Audio(fShort);

const zahrajJednouGecko = ref(true);
const zahrajJednouEfko = ref(true);

function resetujCislo() {
    ukazaneCislo.value = '';
    zahrajJednouGecko.value = true;
    zahrajJednouEfko.value = true;
}

function hrajGecko() {
    if (zahrajJednouGecko.value) {
        zvukGecko.currentTime = 0;
        zvukGecko.play();
        zahrajJednouGecko.value = false;

    }
}

function hrajEfko() {
    if (zahrajJednouEfko.value) {
        zvukEfko.currentTime = 0;
        zvukEfko.play();
        zahrajJednouEfko.value = false;
    }
}



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

    <div class="spravnyKod">
        <p v-if="ukazaneCislo.length === 4 && ukazaneCislo === spravnyPin">
            <span @mouseover="hrajGecko()">Výborně :) Bohužel toto není bankomat.</span>
        </p>
        <p v-else-if="ukazaneCislo.length === 4">
            <span @mouseover="hrajEfko()">Špatně, zkus to znova</span>
        </p>
    </div>


    <button @click="resetujCislo()">Reset</button>



</template>


<style scoped></style>