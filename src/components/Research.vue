<template>
  <section id="research">

    <div class="content">
      <form>
        <input placeholder="Type the product you're looking for" />
        <button type="submit">
          Search
        </button>
      </form>

      <div class="results">
        <ul>
          <li>product 1</li>
          <li>product 2</li>
        </ul>
      </div>
    </div>  

  </section>
</template>

<script>
export default {
  name: 'Research'
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