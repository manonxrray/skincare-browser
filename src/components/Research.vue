<template>
  <section id="research">

    <div class="content">
      <form>
        <input type="text" placeholder="Type the product you're looking for" />
        <button type="submit">
          Search
        </button>
      </form>

      <div class="results">
        <ul v-for="product in products" :key="product.id">
          <li>{{ product.name }}</li>
        </ul>
      </div>
    </div>  

  </section>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Research',
  data() {
    return {
      products: null
    }
  },
  mounted() {
    axios
    .get('https://thawing-scrubland-03171.herokuapp.com/https://skincare-api.herokuapp.com/products')
    .then((response) => {
      this.products = response.data
    })
  }
}
</script>

<style scoped>
#research {
  background-color: #DB0992;
  padding: 1rem;
}

  .content {
    display: grid;
    grid-auto-rows: auto;
    width: 80vw;
    align-items: center;
    margin: auto;
  }

form {
  height: 2rem;
  display: flex;
  justify-content: space-around;
}

input {
  width: 70%;
  border-radius: 5px;
  border: none;
}

button {
  background-color: #55D7FF;
  border: none;
  border-radius: 5px;
  width: 20%
}

.results {
  color: white;
}

@media screen and (min-width: 900px) {
  #research { 
    grid-area: 2 / 1 / 3 / 3;
  }

  form {
    height: 3rem;
  }

}
</style>