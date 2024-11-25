<script setup>
import {ref} from "vue";
import ReaktivitaComputed from "./components/ReaktivitaComputed.vue";
import TernarniOperator from "./components/TernarniOperator.vue";
import DirektivaOn from "./components/DirektivaOn.vue";


const nahodneCislo = ref(Math.floor(Math.random()*50));
setInterval (() => {
  nahodneCislo.value = (Math.floor(Math.random()*50));
},2000 );


</script>


<template>
  <h1> Ahoj :)) Vítám Tě na mé stránce "Studijní úkoly" </h1>
  <h1>David MsF</h1>
  <h2> Webdesign & JavaScript student</h2>
  
  <div class="kartaTri">
    <TernarniOperator />
  </div>

<div class="karta">
  <ReaktivitaComputed />
</div>
<div class="kartaDve">
  <DirektivaOn />
</div>





</template>



<style scoped>



</style>