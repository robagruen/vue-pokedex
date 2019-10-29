<template>
  <div class="header">
    <div class="container">
      <div class="row">
        <div class="col-md-8">
          <h1>PokeAPI</h1>
        </div>
        <div class="col-md-4">
          <input type="text" name="filter" id="filter">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header'
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
