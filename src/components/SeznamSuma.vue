<script setup>
import { ref, computed } from "vue"

const originalPole = ref([5, 9, 7, 6, 2, 1, 3, 4, 10, 8]);
const ukazOriginal = ref(true);
const ukazSeznam = ref(false);
const napis = ref('Zobrazit seznam')
const napisPravda = ref(false);

const serazenePole = computed(() => {
    const kopiePole = [...originalPole.value];
    kopiePole.sort((cisloA, cisloB) => {
        return cisloA - cisloB;
    });
    return kopiePole;
});

function seradPole() {
    originalPole.value = serazenePole.value;
    ukazOriginal.value = false;
}

function resetPole() {
    originalPole.value = [5, 9, 7, 6, 2, 1, 3, 4, 10, 8];
    ukazOriginal.value = true;
}

function toggleSeznam() {
    ukazSeznam.value = !ukazSeznam.value;
    napisPravda.value = !napisPravda.value;

    if (napisPravda.value) {
        napis.value = "Skryj seznam";
    } else {
        napis.value = "Zobrazit seznam";

    }
}

/*  Tady to jde použít taky
const pridaneCislo = computed(() => {
    const kopiePole = [...originalPole.value];
    const nahodneCislo = Math.floor(Math.random() * 100);
    return [...originalPole.value, nahodneCislo];

})
*/
function pridejCislo() {
    const nahodneCislo = Math.floor(Math.random() * 100);
    //originalPole.value = pridaneCislo.value;
    ukazOriginal.value = false;
    originalPole.value.push(nahodneCislo);

}
/*vracim rovnou hodnotu pole-- acc je akumulátor ten to uchová a aktual k tomu přičítá, nula je počáteční hodnota od který se počítá */
const soucetHodnot = computed(() => {
    return originalPole.value.reduce((acc, aktual) => acc + aktual, 0)
})

</script>

<template>
    <div>
        <button @click="toggleSeznam">{{ napis }}</button>


        <div class="seznam" v-if="ukazSeznam">
            <button @click="pridejCislo()"> Přidej random číslo </button>
            <ul><!--Tady jsem musel přidat další key index, protože se mi to duplikovalo a zlobilo to-->
                <li v-for="(cislo, index) in originalPole" :key="index">{{ cislo }}</li>
            </ul>
            <hr>
            <p>{{ soucetHodnot }} celkem</p>

            <button @click="seradPole()">Srovnej čísla</button>
            <button @click="resetPole()">Reset pole</button>

        </div>

    </div>

</template>

<style scoped>
button {
    background-color: #918c5f;
    color: white;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border: none;
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(251, 255, 0, 0.2);
    transition: background-color 0.3s, transform 0.3s;
}

button:hover {
    background-color: #996312;
    transform: scale(1.15);
}

button:active {
    transform: scale(0.95);
}

li {
    ;
}
</style>