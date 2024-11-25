<script setup>
import {ref, computed} from "vue";

const hodnota = ref(0) ;
function pridejHodnotu () {
   if (hodnota.value < 10) {
    hodnota.value++
   }
}

function resetHodnotu() {
    hodnota.value = 0;
}


const vypnoutTlacitko = computed(() => hodnota.value >=10 );

</script>



<template>
    <h2>po dosažení 10ti se tlačítko vypne</h2>
    <button v-on:click="pridejHodnotu()" :disabled="vypnoutTlacitko"> Přidej hodnotu o +1 </button>
    <button v-on:click="resetHodnotu"> Resetuj hodnotu </button>
    <p> {{ hodnota  }}</p>

</template>



<style scoped>

</style>