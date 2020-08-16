<template>
   <div class="container cont">

    <div class="row">

      <div class="col-md-12">
      
        <h1>Como Crear un Buscador en Tiempo Real con Vue JS </h1> 
        
        <input type="text" v-model="buscar" class="form-control" placeholder="Ejemplo: Charmander"/>              

      </div>

    </div>

    <div class="row mt-3">

      <div class="col-md-4" v-for="item in items" v-bind:key="item.id"> 

        <div class="card mb-3">
          <img class="card-img-top" v-bind:src="'img/' + item.img" v-bind:alt="item.nombre">
          <div class="card-body">
            <h3 class="card-title mb-3">{{ item.nombre }}</h3>
            <p class="card-text">
              <strong>Tipo:</strong> {{ item.tipo }} 
            </p>
            <p class="card-text">
              <strong>Fortaleza:</strong> {{ item.fortaleza }} 
            </p>
            <p class="card-text">
              <strong>Debilidad:</strong> {{ item.debilidad }} 
            </p>
          </div>
        </div>

      </div>

    </div>

   </div>
</template>

<script>

import datos from "../assets/json/pokemones.json";

export default {

  // Exporto mi componente 'Pokemones' 
  name: 'Pokemones',
  props: {
    msg: String
  },
  
  // declaro el elemento buscar 
  data() {
    return {
      buscar: ''
    }
  },
    
  // Creo un método llamado 'items' y obtengo los datos de los pokemones
  // Asimismo filtro la búsqueda de los pokemones con el método filter()  
  computed: {
    items() {
      return datos.filter(item => {
        return item.nombre.toLowerCase().includes(this.buscar.toLowerCase());
      });
    },

  }
  
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /**/
</style>
