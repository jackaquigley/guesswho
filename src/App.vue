<template>
  <div id="app">

    <game-board v-if="characters.length":characters="characters"></game-board>

  </div>
</template>

<script>

import GameBoard from './components/GameBoard.vue'

export default {
  name: 'App',
  data() {
    return {
      characters: []
    }
  },
  components: {
    'game-board': GameBoard
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
