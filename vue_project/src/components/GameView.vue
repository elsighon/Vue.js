<template>

  <img class="w-full" alt="Vue banniere" src="../assets/img/banniere.jpg">
  <div class="flex">
    <div class="w-1/5">
      <selection-box
        :selection="selection"
      >
      </selection-box>
    </div>
    

    <div class="w-4/5 mt-2">
      <Game-card 
        v-for="(game, index) in game.games"
        :key="index"
        :game="game"
        @add-Game="addGameToSelection"
        >
      </Game-card>
    </div>
    

  </div>
    
</template>

<script>
import gameData from '../data/games.json'
import GameCard from './GameCard.vue'
import SelectionBox from './SelectionBox.vue'

export default {
  name: "game-view",
  components: {
    GameCard,
    SelectionBox
  },
  data() {
    return {
      game: gameData,
      selection: []
    }
  },
  methods: {
    addGameToSelection(game){
      this.selection.push(game)
      this.$emit('child-event', game)
    }
  }
}
</script>

<style scoped>

</style>