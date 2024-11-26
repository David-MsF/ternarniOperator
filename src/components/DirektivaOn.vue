<script setup>
import { computed, ref } from "vue";

const prvniKostka = ref(0);
const druhaKostka = ref(0);

function hodit() {
    prvniKostka.value = Math.ceil(Math.random() * 6);
    druhaKostka.value = Math.ceil(Math.random() * 6);
}
/* if (prvniKostka.value === druhaKostka.value) {
     vysledek.value = 'Jseš BOREC !!!Výhra!!!';
 } else {
     vysledek.value = 'Bohužel to nevyšlo, házej znovu'
 }
}  */

const vysledek = computed(() => {
    if (prvniKostka.value === druhaKostka.value) {
        return `${prvniKostka.value} a ${druhaKostka.value} Jseš BOREC !!!Výhra!!!`;
    } else {
        return `Házej znovu ${prvniKostka.value} a ${druhaKostka.value} nejsou výherní `;
    }
});

</script>

<template>
    

    <h2> Zahrajeme si :)) Klikni na kostky </h2>
   
    <div class="tlacitka">
        <!--   <button id="hodit" @click="hodit">Hoď kostkami!!</button> -->
        <img class="kostka" src="../assets/image/kostky.jpg" alt="" @click="hodit" style="cursor: pointer;">
    </div>
    <!--<img class = "kostka " src= "/src/image/kostky.jpg" alt=""> -->

    
    <p>První kostka: {{ prvniKostka }}</p>
    <p>Druhá kostka: {{ druhaKostka }}</p>
    <p>Výsledek: {{ vysledek }}</p>


</template>

<style scoped>
h3 {
    font-size: x-large;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    color: rgb(73, 45, 9);
    text-align: center;
}

/*#hodit {
    background-color: aqua;
}

*/

.tlacitka {
    display: flex;
    justify-content: center;
    /* Centrovat horizontálně */
    align-items: center;
    /* Centrovat vertikálně  */
    height: 60px;
}

.kostka {
    width: 60px;
}
</style>