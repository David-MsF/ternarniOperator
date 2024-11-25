<script setup>
import {ref} from "vue";
import ReaktivitaComputed from "./components/ReaktivitaComputed.vue";
import TernarniOperator from "./components/TernarniOperator.vue";
import DirektivaOn from "./components/DirektivaOn.vue";


const nahodneCislo = ref(Math.floor(Math.random()*50));
setInterval (() => {
  nahodneCislo.value = (Math.floor(Math.random()*50));
},2000 );

const activeDiv = ref(null); // Přidáno pro sledování aktivního divu

function toggleDiv(divNumber) {
  activeDiv.value = activeDiv.value === divNumber ? null : divNumber; // Toggle funkce
}
</script>


<template>
  <h1> Ahoj :)) Vítám Tě na mé stránce "Studijní úkoly" </h1>
  <h1>David MsF</h1>
  <h2> Webdesign & JavaScript student</h2>
  
  <div class="kartaTri">
    <span @click="toggleDiv(1)" style="font-size: 2em; cursor: pointer;">Ternární operátor</span>
    <TernarniOperator v-if="activeDiv === 1" />
  </div>

  <div class="karta">
    <span @click="toggleDiv(2)" style="font-size: 2em; cursor: pointer;">Reaktivita computed</span>
    <ReaktivitaComputed v-if="activeDiv === 2" />
  </div>

  <div class="kartaDve">
    <span @click="toggleDiv(3)" style="font-size: 2em; cursor: pointer;">Direktiva v-on</span>
    <DirektivaOn v-if="activeDiv === 3" />
  </div>




</template>



<style scoped>

.kartaTri, .karta, .kartaDve {
  margin-top: 20px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  color: darkseagreen;
}

</style>