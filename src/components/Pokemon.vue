<template>
  <div class="pokemon" :data-pokemon="name">
    <img :src="imgURL" class="pokemon-img" alt="">
    <p class="pokemon-name">{{ name }}</p>
    <p class="pokemon-info"><span class="grass">{{ type1 }}</span> | <span class="poison">{{ type2 }}</span></p>
  </div>
</template>

<script>
export default {
  name: 'Pokemon',
  props: {
    name: String,
    type1: String,
    type2: String
  },
  data: function() {
    return {
      imgSrc: "./../assets/" + this.name + ".svg",
      imgURL: require(imgSrc)
    }
  },
  mounted() {
    console.log(this.imgURL);
  }
}
</script>

<style scoped>
.pokemon {

}

.pokemon-img {
  width: 100%;
}

.pokemon-name {
  text-transform: capitalize;
  text-align: center;
}

.pokemon-info {
  text-align: center;
}

.pokemon-info span {
  text-transform: capitalize;
}

.grass {

}

.fire {

}

.water {

}


</style>
