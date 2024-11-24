<script setup>
import {ref} from "vue";
import ReaktivitaComputed from "./components/ReaktivitaComputed.vue";
const nahodneCislo = ref(Math.floor(Math.random()*50));
setInterval (() => {
  nahodneCislo.value = (Math.floor(Math.random()*50));
},2000 );


</script>


<template>
  <h1>Ternární operátor </h1>
  <h2>Úkol v rámci studia</h2>


<p>Padlo číslo: {{ nahodneCislo  }}</p>
<p>číslo je {{  (nahodneCislo %2===0) ? "sudé" : "liché" }}</p>
<p>číslo je menší než 25: {{  (nahodneCislo < 25) ? "Ano" : "Ne"  }}</p>

<div class="karta">
  <ReaktivitaComputed />
</div>





</template>



<style scoped>



</style>