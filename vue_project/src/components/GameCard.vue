<template>
  <div 
    class="border border-black m-2 p-2 flex justify-between"
    :class="disponibiliteStyle"
  >
    <div>
      <h1 class="text-lg">{{ GameName }}</h1>
    </div>
    <base-button
      text="Sélectionner"
      @click="addToSelection"
    >
    </base-button>
  </div>
</template>

<script>
export default {
  name: "game-card",
  props: ['game'],
  computed: {
    GameName(){
      if(this.game.name.split('.').length > 1){
        return this.game.name.split('.')[1]
      }
      return this.game.name;
    },
    isAvailable() {
      if(this.game.disponibilite == "Indisponible"){
        return true
      }
      return false
    }, 
  },
  methods: {
    addToSelection() {
      this.$emit('add-game', this.game)
    }
  }
}
</script>

<style scoped>

</style>