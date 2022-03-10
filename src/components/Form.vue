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
  @import "../styles/_variables.scss";
  form {
    background: $bg;
    border: 1px solid $color;
    margin: 0 50px 25px;
    padding: 15px 25px 25px;
    text-align: center;
    font-family: 'Courier New', Courier, monospace;
    transform: scale(1);
    transition: .3s transform;
  }
  form:hover {
    transform: scale(1.06);
  }
  button {
    padding: 5px 10px;
    background: $button-color;
    border: 1px solid transparent;
    cursor: pointer;
    transition: border-color 0.15;
  }
  button:hover {
    border-color: $button-color;
  }
  button[disabled] {
    opacity: 0.6;
  }
</style>
