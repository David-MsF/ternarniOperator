<script setup>
import { ref, computed } from "vue";


const obrazky = [
    'bobr1',
    'bobr2',
    'bobr3',
    'bobr4',
    'bobr5',
    'bobr6'
];
const vybranyBobr = ref(obrazky[0]);
const zobrazitObrazek = ref(false);

function zmenBobra() {
    const nahodnyIndex = Math.floor(Math.random() * obrazky.length);
    vybranyBobr.value = obrazky[nahodnyIndex];
    zobrazitObrazek.value = true;
}

const dynamickaCesta = computed(() => {
    return new URL(`../assets/image/${vybranyBobr.value}.jpg`, import.meta.url).href;
});


</script>

<template>
    <h2>Stiskem tlačítka zvolíš náhodný obrázek bobra</h2>
    <button @click="zmenBobra()">Bober</button>
    <p v-if="zobrazitObrazek">
        <img :src="dynamickaCesta" alt="Bober" />
    </p>
</template>

<style scoped>
img {
    width: 250px;
}
</style>