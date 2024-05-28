<script>

export default {
    props: {
        carta: String,
        cardName: String,
        percorso: String,
        cardAttribute: String,
        cardArchetype: String,
    },
    data() {
        return {

        }
    },
    methods: {

    },
    mounted() {

    }


}
</script>


<template>
    <li>
        <img :src="percorso" alt="">
        <div>
            {{ cardName.toUpperCase() }}
        </div>
        <div>

            {{ cardAttribute }}
            {{ cardArchetype }}

        </div>
    </li>
</template>


<style scoped>
li {
    padding: 10px;
    width: calc(100% / 5 - 20px);
    list-style-type: none;
    text-align: center;
}

img {
    width: 100%;
}

div {
    padding: 1rem;
}
</style>
