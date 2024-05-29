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
            appTitle: "Yu-Gi-Oh Api",

            appLinks,

            Store,

            prova: ""

        }
    },
    methods: {

    },
    created() {
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then(risultato => {
            console.log(risultato.data.data);
            this.Store.carte = risultato.data.data
        });
    },
    mounted() {

    }


}
</script>


<template>
    <AppHeader :title="appTitle" :links="appLinks" />
    <input type="text" v-model="appTitle">
    <main>
        <ListaCarte />
    </main>
</template>


<style scoped>
main {
    padding: 1rem;
    width: 80%;
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}
</style>
