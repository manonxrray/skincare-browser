<template>
  <section id="research">

    <div class="content">

      <!--
        Creating a form to display the research bar
        NOTE : The Search button is not currently useful because the research is dynamic
        I'm going to look for a solution in my free time
      -->

      <form>
        <!-- Connecting the input to the input prop setup in data (l.39) with v-model -->
        <input type="text" v-model="input" placeholder="Type the product you're looking for" />
        <button>
          Search
        </button>
      </form>

      <div class="results">
        <!-- Looking for the right products in our filtered list and displaying their brand and name -->
        <ul v-for="product in this.filteredProducts()" :key="product.id">
          <li><span class="product-brand">{{product.brand}}</span> - {{ product.name }}</li>
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
      products: null,
      input: ""
    }
  },
  methods: {
    fetchProducts() {
      axios
      .get('https://thawing-scrubland-03171.herokuapp.com/https://skincare-api.herokuapp.com/products')
      .then((response) => {
        this.products = response.data
      })
    },
    // It will return every product whose name includes what is written in the research input
    filteredProducts() {
      return this.products.filter((product) =>
        product.name.includes(this.input.toLowerCase()) 
      );
    },
  },
  created() {
    /* 
      I couldn't have my code working if I didn't call this function in the created() part
      but the thing is products are all setup when no research is made
      All my products are loaded before the filteredProducts function is called
    */
    this.fetchProducts()
  }
}
</script>

<style scoped>
#research {
  background-color: #DB0992;
  padding: 1rem;
  overflow: scroll;
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
  padding: 1rem;
  outline: none;
}

button {
  background-color: #55D7FF;
  border: none;
  border-radius: 5px;
  width: 20%;
}

button:hover {
  cursor: pointer;
}

.results {
  color: white;
}

.product-brand {
  text-transform: uppercase;
  font-weight: bold;
}

@media screen and (min-width: 900px) {
  #research { 
    grid-area: 2 / 1 / 3 / 3;
  }

  form {
    height: 3rem;
  }

  button {
     font-size: 1.2rem;
  }

}
</style>