<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <form :key="movie.name" v-for="movie in movies">
      <h3>{{ movie.name }}</h3>
      <button 
        type="button"
        v-on:click="movie.quantity -= 1"
        v-bind:disabled="movie.quantity === 0"
      >-</button>
      <p>{{ movie.quantity }}</p>
      <button 
        type="button"
        v-on:click="movie.quantity += 1"
        v-bind:disabled="movie.quantity === movie.available"
      >+</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Form',
  props: {
    title: String
  },
  data() {
    return {
      movies: [
        {
          name: 'spide-man',
          available: 5,
          quantity: 0,
        },
        {
          name: 'iron-man',
          available: 7,
          quantity: 0,
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  h3 {
    margin: 40px 0 0;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>
