<script>
import AppHeader from './components/AppHeader.vue';
import appLinks from './data/AppHeaderLinks.js';
import ListaCarte from './components/ListaCarte.vue';
import Store from './data/store.js';
import axios from 'axios';

export default {
    components: {
        AppHeader,
        ListaCarte,

    },
    data() {
        return {
            appTitle: "Yu-G-Oh API",

            cercaCarta: "mage",

            appLinks,

            Store,

            prova: "",

        }
    },
    methods: {
        getCarte() {

            axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?&fname=" + this.cercaCarta).then(risultato => {
                this.Store.carte = risultato.data.data
            });
        }
    },
    created() {
        this.getCarte();

        axios.get("https://db.ygoprodeck.com/api/v7/archetypes.php").then(result => {
            console.log(result.data);
            this.Store.archetypes = result.data;
            this.prova = result.data
        })
    },
    mounted() {

    }


}
</script>


<template>
    <AppHeader :title="appTitle" :links="appLinks" />
    <select v-model="cercaCarta" @click="getCarte">
        <option v-for="archetipo in Store.archetypes">{{ archetipo.archetype_name }}</option>
    </select>
    <button @click="getCarte">cerca</button>
    <input v-model="cercaCarta" type="text" @keyup.enter="getCarte">
    <main>
        <ListaCarte />
        <!-- <pre>{{ prova }}</pre> -->
    </main>
</template>


<style scoped>
main {
    padding: 1rem;
    width: 80%;
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
</style>
