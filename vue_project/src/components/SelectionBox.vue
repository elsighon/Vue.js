<template>
  <div class="border border-black text-center m-4 p-4">
    Selection : {{ selection.length }}
    <span v-if="numberSelection">jeu</span>
    <span v-else>jeux</span>

    <ul>
      <li v-for="jeux in selection" :key="jeux.name">{{ jeux.name }}</li>
    </ul>

  </div>
  
</template>

<script>
export default {
  name: "selection-box",
  props: ['selection'],
  computed: {
    numberSelection(){
      if(this.selection.length < 2){
        return true
      }
      return false
    }
  }

}
</script>

<style>

</style>