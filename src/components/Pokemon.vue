<template>
  <div class="col-lg-2 col-md-4 col-sm-6 pokemon" :id="number" :data-pokemon="name">
    <img :src="spriteURL" class="pokemon-img" alt="">
    <p class="pokemon-name">{{ name }}</p>

    <p v-if="type2" class="pokemon-info"><span :class="type1">{{ type1 }}</span> | <span :class="type2">{{ type2 }}</span></p>
    <p v-else class="pokemon-info"><span :class="type1">{{ type1 }}</span></p>
  </div>
</template>

<script>
import { isNullOrUndefined } from 'util';

export default {
  name: 'Pokemon',
  props: {
    name: String,
    number: Number,
    spriteURL: String,
    type1: String,
    type2: String    
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
