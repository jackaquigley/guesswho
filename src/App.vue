<template>
  <div id="app">

  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      characters: []
    }
  },
  components: {

  },
  mounted() {
      fetch('https://codeclan-guess-who.herokuapp.com/api/characters')
      .then(res => res.json())
      .then(data => this.characters = data)

  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
