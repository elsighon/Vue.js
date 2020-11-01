<template>
  <div class="bg-blue-300 p-2">
    <a href="#" @click="changeComponent('game-view')">Tous les jeux</a> | 
    <a href="#" @click="changeComponent('selection-list')">Mon panier</a>
  </div>
</template>

<script>
export default {
  name: "nav-bar",
  methods: {
    changeComponent(value) {
      this.$emit('change-component', value)
    }
  }
}
</script>

<style>

</style>