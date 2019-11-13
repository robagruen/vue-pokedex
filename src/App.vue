<template>
  <div id="app" class="pokedex">
    <Header />
    <div class="container pokedex-wrapper">
      <div class="row pokedex-entries">
        <div v-for="pokemon in pokelist" class="col-lg-2 col-md-4 col-sm-6 pokemon-wrapper">
          <Pokemon 
            v-if="pokemon['data']['types'].length == 2"
            :name="pokemon['data']['name']"
            :number="pokemon['data']['id']"
            :spriteURL="pokemon['data']['sprites']['front_default']"
            :type1="pokemon['data']['types'][0]['type']['name']"
            :type2="pokemon['data']['types'][1]['type']['name']"
          />
          <Pokemon
            v-else
            :name="pokemon['data']['name']"
            :number="pokemon['data']['id']"
            :spriteURL="pokemon['data']['sprites']['front_default']"
            :type1="pokemon['data']['types'][0]['type']['name']"
            type2="none"
          />
        </div>
      </div>
    </div>
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
      pokelist: []
    }
  },
  mounted() {
    for (let i = 1; i < 152; i++) {
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
