<script setup>
import {ref, computed} from "vue"
/*const poleCisel = ref([11, 74, 45, 85, 66]);
function zjistitSumu() {
    let sumaPole = 0;
for ( let cislo of poleCisel.value) {
    sumaPole += cislo;
}
return sumaPole;
}

const sumaComputed = computed(() => {
    let sumaPole = 0;
for ( let cislo of poleCisel.value) {
    sumaPole += cislo;
}
return sumaPole
});

setTimeout( () => {
    poleCisel.value.push(Math.floor(Math.random()* 100))
}, 2000);
*/
const cisloDelka = ref(Math.floor(Math.random() * 100));
const cisloVyska =ref(Math.floor(Math.random() * 100));
const obsahObdelniku = computed( () => {
    return cisloDelka.value*cisloVyska.value;

}); 

setInterval( () => {
    cisloDelka.value = Math.floor(Math.random() * 100);
    cisloVyska.value = Math.floor(Math.random() * 100);


}, 2000);

</script>


<template>
    <h2>Náhodné generování obdélníku</h2>
    <!--<p>pole čísel: {{  poleCisel }}</p>
    <p>suma pole ( function ): {{ zjistitSumu() }}</p> !!! dává zabrat PC 
    <p>suma pole (computed): {{ sumaComputed%2 ? "sudé" : "liché" }}</p>
    <p> suma : {{ sumaComputed }}</p>   -->
    <p>Délka  : {{  cisloDelka }} cm</p>
    <p>Výška  : {{  cisloVyska }} cm</p>
    <p>Obsah obdelníku : {{  obsahObdelniku }} cm</p>



</template>
    


<style scoped>

</style>