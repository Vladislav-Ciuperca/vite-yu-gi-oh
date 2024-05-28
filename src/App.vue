<script>
import AppHeader from './components/AppHeader.vue';
import appLinks from './data/AppHeaderLinks.js';
import ListaCarte from './components/ListaCarte.vue';
export default {
    components: {
        AppHeader,
        ListaCarte,
    },
    data() {
        return {
            appTitle: "Yu-Gi-Oh Api",

            appLinks

        }
    },
    methods: {

    },
    mounted() {

    }


}
</script>


<template>
    <AppHeader :title="appTitle" :links="appLinks" />
    <input type="text" v-model="appTitle">
    <main>
        <!-- <h1>Benvenuto in {{ appTitle }}</h1> -->
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
