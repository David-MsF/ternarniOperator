<script setup>
import { ref, computed } from "vue";
/*
const vlastniNadpis = ref('');
const barvaTextu = ref('#175468');
const stylPisma = ref("italic")


*/

const vlastniNadpis = ref({
    text: 'Napište svůj text',
    color: '#175468',
    fontStyle: 'normal',
    fontWeight: 'normal'
});

const barvaNadpisu = computed(() => {
    return {
        color: vlastniNadpis.value.color,
        fontStyle: vlastniNadpis.value.fontStyle,
        fontWeight: vlastniNadpis.value.fontWeight,
        fontFamily: vlastniNadpis.value.fontFamily
    }
});

</script>

<template>
    <h4 :style="barvaNadpisu">{{ vlastniNadpis.text }}</h4>
    <div>
        <input v-model="vlastniNadpis.text" type="text">

        <!--Tady jsem mysel, že to budu mít hned :D a pořád jsem tam cpal :style :D :D jj je to v-model pro příště :D -->

        <select v-model="vlastniNadpis.fontFamily">
            <option disabled  >Vyber písmo</option>
            <option value="Cursive">Cursive</option>
            <option value="fantasy">fantasy</option>
            <option value="sans-serif">sans-serif</option>
        </select>
        <input v-model="vlastniNadpis.color" type="color">

    </div>
    <div>
        <p>Styl písma: {{ vlastniNadpis.fontStyle }} , {{ vlastniNadpis.fontWeight }}, {{ vlastniNadpis.fontFamily }}
        </p>

        <label> Kurzíva</label>
        <input false-value="normal" v-model="vlastniNadpis.fontStyle" type="checkbox" true-value="italic">

        <label> Tučně</label>
        <input type="checkbox" v-model="vlastniNadpis.fontWeight" false-value="normal" true-value="bold">




    </div>






</template>




<style scoped></style>