<script setup>
import {ref, watch} from "vue";

const coPises = ref("");
const stav = ref("nic");
let prazdnyInput = '';



watch(coPises, (novaHodnota) => {
    if(novaHodnota.length > prazdnyInput.length){
        stav.value = "Píšeš....";
    }else if (novaHodnota.length < prazdnyInput.length){
        stav.value = "Mažeš...";
    }else {
        stav.value = "nic"
    }
    prazdnyInput = novaHodnota;
}, { immediate: true });

</script>


<template>
    <h2>Píšeš nebo mažeš?</h2>
    <div class="divik">
        <label> Napiš něco
            <input v-model="coPises" type="text">
        </label>
        <p>{{ stav }}</p>
    </div>


</template>




<style scoped>
.divik {
    min-height: 5rem;
    color: aquamarine;
}
</style>