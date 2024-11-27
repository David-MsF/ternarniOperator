<script setup>
import { ref, computed } from "vue";

const barvaPozadi = ref('#ff0000')
function ZmenBarvu() {
    const randomBarva = `#${Math.floor(Math.random() * 16777215).toString(16)}`;
    barvaPozadi.value = randomBarva;

}

const koleckoRadius50 = ref('50%');
function zmenRadius(radius) {
    koleckoRadius50.value = radius;
}

const koleckoSirka = ref('10rem');
function zmenSirku(sirka) {
    koleckoSirka.value = sirka;
}

const koleckoVyska = ref('10rem');
function zmenVysku(vyska) {
    koleckoVyska.value = vyska;
}

</script>



<template>

    <h2>Uprav si kolečko :)</h2>
    <p>
        <button class="barva" @click="ZmenBarvu()">Random barva</button>

    </p>
    <p>
        <button class="radius" @click="zmenRadius('40%')">Radius 40%</button>
        <button class="radius" @click="zmenRadius('50%')">Radius 50%</button>
        <button class="radius" @click="zmenRadius('25%')">Radius 25%</button>
        <button class="radius" @click="zmenRadius('10%')">Radius 10%</button>
    </p>
    <p>
        <button class="sirka" @click="zmenSirku('15rem')">Šířka 15 rem</button>
        <button class="sirka" @click="zmenSirku('5rem')">Šířka 5 rem</button>
        <button class="sirka" @click="zmenSirku('10rem')">Šířka 10 rem</button>
        <button class="sirka" @click="zmenSirku('20rem')">Šířka 20 rem</button>
    </p>
    <p>
        <button class="vyska" @click="zmenVysku('10rem')">Výška 10 rem</button>
        <button class="vyska" @click="zmenVysku('15rem')">Výška 15 rem</button>
        <button class="vyska" @click="zmenVysku('5rem')">Výška 5 rem</button>
        <button class="vyska" @click="zmenVysku('20rem')">Výška 20 rem</button>
    </p>







    <div class="container">
        <div class="kolecko"
            :style="{ backgroundColor: barvaPozadi, borderRadius: koleckoRadius50, width: koleckoSirka }">
        </div>
    </div>




</template>



<style scoped>
.kolecko {
    width: v-bind(koleckoSirka);
    height: v-bind(koleckoVyska);

    border-radius: v-bind(koleckoRadius50);
    transition: 0.8s;


}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 21rem;
    /* Výška rodičovského divu, aby bylo kolečko ve středu stránky */
}

.barva {
    background-color: #7db47e;
    color: white;
    padding: 10px 20px;
    /* Vnitřní okraje (top/bottom 15px, left/right 32px) */
    text-align: center;
    text-decoration: none;
    display: inline-block;
    /* Inline blok, aby se tlačítko chovalo jako blokový prvek */
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border: none;
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(251, 255, 0, 0.2);
    /* Stín pro efekt 3D */
    transition: background-color 0.3s, transform 0.3s;
    /* Přechod pro změnu barvy a transformaci */
}

.barva:hover {
    background-color: #007706;
    transform: scale(1.05);
}

.barva:active {
    transform: scale(0.95);
    /* Zmenšení tlačítka při kliknutí */
}

.sirka {
    background-color: #445c88;
    color: rgb(255, 255, 255);
    padding: 10px 20px;
    /* Vnitřní okraje (top/bottom 15px, left/right 32px) */
    text-align: center;
    text-decoration: none;
    display: inline-block;
    /* Inline blok, aby se tlačítko chovalo jako blokový prvek */
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border: none;
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(251, 255, 0, 0.2);
    /* Stín pro efekt 3D */
    transition: background-color 0.3s, transform 0.3s;
    /* Přechod pro změnu barvy a transformaci */
}

.sirka:hover {
    background-color: #032bb1;
    transform: scale(1.15);
}

.sirka:active {
    transform: scale(0.95);
    /* Zmenšení tlačítka při kliknutí */
}

.radius {
    background-color: #86637d;
    color: white;
    padding: 10px 20px;
    /* Vnitřní okraje (top/bottom 15px, left/right 32px) */
    text-align: center;
    text-decoration: none;
    display: inline-block;
    /* Inline blok, aby se tlačítko chovalo jako blokový prvek */
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border: none;
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(251, 255, 0, 0.2);
    /* Stín pro efekt 3D */
    transition: background-color 0.3s, transform 0.3s;
    /* Přechod pro změnu barvy a transformaci */
}

.radius:hover {
    background-color: #770053;
    transform: scale(1.15);
}

.radius:active {
    transform: scale(0.95);
    /* Zmenšení tlačítka při kliknutí */
}

.vyska {
    background-color: #918c5f;
    color: white;
    padding: 10px 20px;
    /* Vnitřní okraje (top/bottom 15px, left/right 32px) */
    text-align: center;
    text-decoration: none;
    display: inline-block;
    /* Inline blok, aby se tlačítko chovalo jako blokový prvek */
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border: none;
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(251, 255, 0, 0.2);
    /* Stín pro efekt 3D */
    transition: background-color 0.3s, transform 0.3s;
    /* Přechod pro změnu barvy a transformaci */
}

.vyska:hover {
    background-color: #996312;
    transform: scale(1.15);
}

.barva:active {
    transform: scale(0.95);
    /* Zmenšení tlačítka při kliknutí */
}
</style>