<template>
  <div id="app">
    <caixas/> <br>
    <ferramentas @alteraCor="alteraCor($event)" @alterouTexto="alterarTexto($event)"/>
  </div>
</template>

<script>
import Caixas from "./components/Caixas.vue"
import Ferramentas from "./components/Ferramentas.vue"
export default {
  name: 'App',
  components: { 
    Caixas, Ferramentas
  }, data: function() {
    return{
      
    }
  }
}
</script>

<style>
</style>
