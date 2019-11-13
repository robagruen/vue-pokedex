<template>
  <div class="header">
    <div class="container">
      <div class="row">
        <div class="col-lg-8 col-md-6">
          <h1>PokeAPI</h1>
        </div>
        <div class="col-lg-4 col-md-6">
          <input type="text" name="filter" id="filter" @change="filterPokemon" placeholder="Filter Pokemon">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  mounted() {
    // Component mounted
  },
  methods: {
    filterPokemon (input) {
      let filterText = input["srcElement"].value;
      let filter = "[data-pokemon*='" + filterText + "']";
      let allPokemon = document.querySelectorAll(".pokemon-wrapper");
      let pokemon = document.querySelectorAll(filter);
      
      if (filterText == "") {
        console.log("if");
        for (let i = 0 ; i < allPokemon.length; i++) {
          allPokemon[i].style.display = "";
        }
      }
      else {
        console.log("else");
        for (let i = 0 ; i < allPokemon.length; i++) {
          allPokemon[i].style.display = "none";
        }
        for (let i = 0; i < pokemon.length; i++) {
          pokemon[i]["parentElement"].style.display = "";
        }
      }
    }
  }
}
</script>

<style scoped>
.header {
  background: #B72525;
  height: 80px;
}

h1 {
  margin: 0;
  line-height: 80px;
  color: white;
}

#filter {
  width: 100%;
  border-radius: 20px;
  padding-left: 20px;
  height: 40px;
  margin: 20px 0;
  border: none;
}
</style>
