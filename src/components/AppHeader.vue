<script>
import Store from '../data/store.js'

export default {
  name: "AppHeader",
  props: {
    title: String,
    links: Array
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
  <header>
    <h1>{{ title }}</h1>
    <ul>
      <!-- <li v-for="prova in links">
        <a :href="prova.link">{{ prova.text }}</a>
      </li> -->
    </ul>
  </header>
</template>


<style scoped>
header {
  background: rgb(255, 255, 255);
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  color: #111;
}

ul {
  list-style-type: none;
}

li {
  display: inline-block;
  padding: 0 1rem
}

a {
  text-decoration: none;
  color: unset;
}
</style>
