<template>
  <div id="app">
    <Header />
    <div class="container">
      <div class="row">
        <Pokemon v-for="pokemon in pokelist" :name="pokemon['data']['name']" :number="pokemon['data']['id']" :spriteURL="pokemon['data']['sprites']['front_default']" type1="grass" type2="poison" />
      </div>
    </div>
    <p>{{ info }}</p>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Pokemon from './components/Pokemon.vue'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    Header,
    Pokemon
  },
  data: function() {
    return {
      items: [
        { message: 'Foo' },
        { message: 'Bar' },
        { message: 'Foo' },
        { message: 'Bar' },
        { message: 'Foo' },
        { message: 'Bar' },
        { message: 'Foo' },
        { message: 'Bar' }
      ],
      pokelist: []
    }
  },
  mounted() {
    for (let i = 0; i < 151; i++) {
      axios
        .get('https://pokeapi.co/api/v2/pokemon/' + i + '/')
        .then(response => (this.pokelist.push(response)))
    }
  }
}
</script>

<style>
body {
  margin: 0;
}
</style>
