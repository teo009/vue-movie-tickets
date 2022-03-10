<template>
  <Form title="Películas"/>
</template>

<script>
import Form from './components/Form.vue'

export default {
  name: 'App',
  components: {
    Form
  }
}
</script>

<style lang="scss">
  @import "./styles/_variables.scss";

  #app {
    //font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    //color: #2c3e50;
    margin-top: 60px;
  }
  html, body {
    background: $bg;
    color: $color;
    margin: 0;
    font-family: sans-serif;
  }
  h1 {
    border-bottom: 1px solid $color;
    padding-bottom: 40px;
  }
</style>
