<template>
  <header>
    <section class="text">
      <h1>This is a page for beauty product search</h1>
    </section>
    <section class="picture" />
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
header {
  width: 96vw;
  height: 50vh;
  display: grid;
  grid-auto-rows: 50%;
  background-color: #55D7FF;
};

.text {
  background-color: black;
}

.picture {
  background-image: url("../../resources/beauty-products.jpg");
  background-size: cover;
}


</style>