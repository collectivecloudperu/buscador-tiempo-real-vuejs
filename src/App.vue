<template>
  <div id="app">
    <!-- Muestro el componente 'Pokemones' en el template de 'App.vue' -->
    <Pokemones/>
  </div>
</template>

<script>
  //import HelloWorld from './components/HelloWorld.vue'

  // Importo el componente 'Pokemones' 
  import Pokemones from './components/Pokemones.vue'
   
  export default {
    name: 'App',
    components: {
      Pokemones
    }
  }
</script>

<style>
  #app {
    /* */
  }
</style>
