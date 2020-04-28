<template lang="html">
  <div>

    <mystery-character :randomCharacter="randomCharacter"></mystery-character>

    <character-list v-for="(character, index) in characters" :character="character" :key="index"></character-list>

  </div>
</template>

<script>

import CharacterList from './CharacterList.vue'
import MysteryCharacter from './MysteryCharacter.vue'

export default {
  name: 'game-board',
  props: ['characters'],
  data() {
    return {
    randomCharacter: null
  }
  },
  components: {
    'character-list': CharacterList, 'mystery-character': MysteryCharacter
  },
  mounted(){
    // randomCharacter: function() {
    //   // return Math.floor(Math.random() * 25)
    // }
    this.randomCharacter = this.calculateRandomNumber()
  },
  methods: {
    calculateRandomNumber: function() {
      return Math.floor(Math.random() * 25)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
