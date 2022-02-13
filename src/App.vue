<template>
  <div id="app">
    <h1>Jogo da Forca</h1>
    <section v-if="tela === 'inicio'" id="inicio">
      <Formulario title='Defina a Palavra' button='Próximo'/>
      <Formulario title='Defina a Dica' button='Iniciar o Jogo 😃'/>
    </section>
    <section v-if="tela === 'jogo'" id="jogo">
      Jogo
    </section>
  </div>
</template>

<script>
import './css/global.css'
import Formulario from './components/Formulario.vue'

export default {
  name: 'App',
  data() {
    return {
      tela: 'inicio'
    }
  },
  components: {
    Formulario
  }
}
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
