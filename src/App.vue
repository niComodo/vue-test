<template>
    <div id="app">
        <alert/>
        <img alt="Vue logo" src="./assets/logo.png">
        <div>
            price:
            <input type="number" v-model="price">
        </div>
        <div>
            quantità:
            <input type="number" v-model="qta">
        </div>
        <counter-facile></counter-facile>
        <counter-facile v-model="qta"></counter-facile>
        <counter-facile :value="qta" @input="qta = $event"></counter-facile>
        <!--<counter :price="parseFloat(price)" v-model="qta"></counter>-->
        <!--<counter :price="parseFloat(price)" :value="qta" @input="qta = $event"></counter>-->
    </div>
</template>

<script>

import Alert from "@/components/Alert";
// import Counter from "@/components/Counter";
import CounterFacile from "@/components/CounterFacile";

export default {
    name: 'App',
    data() {
        return {
            qta: 3,
            price: 25
        };
    },
    components: {
        // Counter,
        CounterFacile,
        Alert,
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
