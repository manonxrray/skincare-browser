<template>
  <div id="app">
    <section class="text">
      <h1>This is a page for beauty product search</h1>
    </section>
    <section class="picture" />
    <Research />
  </div>
</template>

<script>
import Research from "./components/Research.vue"

export default {
  name: 'app',
  components: {
    Research
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  width: 100vw;
  height: 100vh;
  display: grid;
  grid-auto-rows: 50%;
}

.text {
    background-color: #55D7FF;
    text-align: center;
    display: table;
}

h1 {
  display: table-cell;
  vertical-align: middle;
  padding: 2rem;
}

.picture {
  background-image: url("../resources/beauty-products.jpg");
  background-size: cover;
}

@media screen and (min-width: 900px) {
  #app {
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(2, 1fr);
  }

  .text {
    grid-area: 1 / 1 / 2 / 2;
  }

  .picture {
    grid-area: 1 / 2 / 2 / 3;
  }
}

</style>
