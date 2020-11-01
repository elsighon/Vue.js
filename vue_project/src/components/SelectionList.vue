<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Ma sélection</h1>

    <div v-if="selection.length == 0">
      <p>Aucun jeu sélectionné</p>
    </div>
    <div v-else>
      <div
        v-for="game in selection"
        :key="game.name" 
        class="bg-gray-400 text-center border border-black my-4 p-2"
      >
      <h3>{{ game.name }} {{ game.prix }}</h3>
        <img class="mx-auto" :src="require('../assets/img/' + game.photo)" alt="">
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
  name: "selection-list",
  props: ['selection'],
}
</script>

<style>

</style>