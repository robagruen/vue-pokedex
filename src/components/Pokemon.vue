<template>
  <div class="pokemon" :id="number" :data-pokemon="name">
    <img :src="spriteURL" class="pokemon-img" alt="">
    <p class="pokemon-name">{{ name }}</p>
    <p v-if="type2 != 'none'" class="pokemon-info"><span :class="type1">{{ type1 }}</span> | <span :class="type2">{{ type2 }}</span></p>
    <p v-else class="pokemon-info"><span :class="type1">{{ type1 }}</span></p>
  </div>
</template>

<script>
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

.normal {
 color:#aa9
}
.fire {
 color:#f42
}
.water {
 color:#39f
}
.electric {
 color:#fc3
}
.grass {
 color:#7c5
}
.ice {
 color:#6cf
}
.fighting {
 color:#b54
}
.poison {
 color:#a59
}
.ground {
 color:#db5
}
.flying {
 color:#89f
}
.psychic {
 color:#f59
}
.bug {
 color:#ab2
}
.rock {
 color:#ba6
}
.ghost {
 color:#66b
}
.dragon {
 color:#76e
}
</style>
