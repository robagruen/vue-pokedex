<template>
  <div id="app" class="pokedex">
    <Header />
    <div class="container pokedex-wrapper">
      <div class="row pokedex-entries">
        <Pokemon 
          v-for="pokemon in pokelist"
          :name="pokemon['data']['name']"
          :number="pokemon['data']['id']"
          :spriteURL="pokemon['data']['sprites']['front_default']"
          :type1="pokemon['data']['types'][0]['type']['name']"
          :type2="pokemon['data']['types'][1]['type']['name']"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Pokemon from './components/Pokemon.vue'
import axios from 'axios'
import { isNullOrUndefined } from 'util'

export default {
  name: 'app',
  components: {
    Header,
    Pokemon
  },
  data: function() {
    return {
      pokelist: []
    }
  },
  mounted() {
    for (let i = 1; i < 152; i++) {
      axios
        .get('https://pokeapi.co/api/v2/pokemon/' + i + '/')
        .then(response => (this.pokelist.push(response)))

        console.log(isNullOrUndefined(pokelist[(i-1)]['data']['types'][1]['type']['name']));

        if (isNullOrUndefined(pokelist[(i-1)]['data']['types'][1]['type']['name'])) {
          console.log(pokelist[(i-1)]['data']['name']);
        }
    }
  },
  computed: {
    someFunction: function() {
      console.log("some console log");
    }
  }
}
</script>

<style>
body {
  margin: 0;
}
</style>
