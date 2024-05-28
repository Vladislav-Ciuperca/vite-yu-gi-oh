<script>
import Carta from './Carta.vue'
import Store from '../data/store.js'

export default {
    components: {
        Carta
    },
    data() {
        return {
            Store
        }
    },
    methods: {

    },
    mounted() {

    }


}
</script>


<template>
    <Carta v-for="carta in Store.carte" :cardName="carta.name" :percorso="carta.card_images[0].image_url"
        :cardArchetype="carta.archetype" :cardAttribute="carta.attribute" />


</template>


<style scoped></style>