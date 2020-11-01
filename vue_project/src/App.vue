<template>
  <nav-bar
    @change-component="changeSelectedComponent"
  >
  </nav-bar>
  
  <keep-alive include="game-view">
    <component 
      :is="selectedComponent"
      v-bind="currentProps"
      @child-event="selectionUpdate"
    >
    </component>
  </keep-alive>
  
</template>

<script>

import GameView from './components/GameView.vue'
import SelectionList from './components/SelectionList.vue'
import NavBar from './components/navigation/NavBar.vue'

export default {
  name: 'App',
  components: {
    GameView,
    SelectionList,
    NavBar
  },
  data() {
    return {
      selectedComponent: 'game-view',
      gameSelection: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "selection-list"){
        return { selection: this.gameSelection }
      }
      return false
    },
  },
  methods: {
    changeSelectedComponent(value) {
      this.selectedComponent = value
    },
    selectionUpdate(value) {
      this.gameSelection.push(value)
    }
  }
}
</script>

<style>
 
</style>
