<template>
  <div id="app">
    <Header />
    <div class="container">
      <div class="row">
        <div v-for="item in items" class="col-lg-2 col-md-4">
          <Pokemon name="abra" type1="grass" type2="poison" />
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Pokemon from './components/Pokemon.vue'

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
      ]
    }
  },
}
</script>

<style>
body {
  margin: 0;
}
</style>
