<script setup>
import { ref, computed } from "vue";

const hodnotaButton = ref(5);
const pridaniMaxu = ref('');

    function zmenHodnotu() {
    hodnotaButton.value--;
    if (hodnotaButton.value === 0) {
        pridaniMaxu.value = "maximalizace";
        setTimeout(() => {
            pridaniMaxu.value = "";
            hodnotaButton.value = 5; 
        }, 3000); 
    }};


</script>



<template>
    <h2>Zvětši Bobra</h2>
    <p>Po dosažení 0 na tlačítku se obrázek na 3 sekundy zvětší. Poté se vše vrátí do původního stavu.</p>

    <button class="but" @click="zmenHodnotu">{{ hodnotaButton }}</button>

    <p>
        <img :class="pridaniMaxu" src="../assets/image/bobr1.jpg" alt="">
    </p>


</template>




<style scoped>
img {
    width: 5rem;
}

.maximalizace {
    width: 30rem;
}
.but {
    background-color: #7db47e; 
    color: white; 
    padding: 15px 32px; /* Vnitřní okraje (top/bottom 15px, left/right 32px) */
    text-align: center; 
    text-decoration: none; 
    display: inline-block; /* Inline blok, aby se tlačítko chovalo jako blokový prvek */
    font-size: 16px; 
    margin: 4px 2px; 
    cursor: pointer; 
    border: none; 
    border-radius: 12px; 
    box-shadow: 0 4px 8px rgba(251, 255, 0, 0.2); /* Stín pro efekt 3D */
    transition: background-color 0.3s, transform 0.3s; /* Přechod pro změnu barvy a transformaci */
}

.but:hover {
    background-color: #00ff0d; /* Změna barvy pozadí při najetí myší */
    transform: scale(1.05); /* A zvětšení tlačítka při najetí myší */
}

.but:active {
    transform: scale(0.95); /* Zmenšení tlačítka při kliknutí */
}


</style>
