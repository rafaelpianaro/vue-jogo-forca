<template>
  <div id="app">
    <h1>Jogo da Forca</h1>
    <section v-if="tela === 'inicio'" id="inicio">
      <Formulario :action="setPalavra" v-if="etapa === 'palavra'" title='Defina a Palavra' button='Próximo'/>
      <Formulario :action="setDica" v-if="etapa === 'dica'" title='Defina a Dica' button='Iniciar o Jogo 😃'/>
    </section>
    <section v-if="tela === 'jogo'" id="jogo">
      <Jogo :jogarNovamente="jogarNovamente" :jogar="jogar" 
        :letras="letras" :etapa="etapa" :verificarLetra="verificarLetra"
        :erros="erros" :palavra="palavra" :dica="dica"
      />
    </section>
  </div>
</template>

<script>
import './css/global.css'
import Formulario from './components/Formulario.vue'
import Jogo from './components/Jogo.vue'

export default {
  name: 'App',
  data: function() {
    return {
      tela: 'inicio',
      etapa: 'palavra',
      palavra: '',
      dica: '',
      erros: 0,
      letras: []
    }
  },
  components: {
    Formulario,
    Jogo
  },
  methods: {
    setPalavra(palavra) {
      // alert(palavra)
      this.palavra = palavra
      this.etapa = 'dica'
    },
    setDica(dica) {
      // alert(palavra)
      this.dica = dica
      this.tela = 'jogo'
      this.etapa = 'jogo'
    },
    verificarLetra(letra) {
      return this.letras.find(item => item.toLowerCase() === letra.toLowerCase())
    },
    jogar(letra) {
      // adiciona letra jogada
      this.letras.push(letra)
      // validar o erro
      this.verificarErros(letra)

    },
    verificarErros(letra) {
      // acerto
      if (this.palavra.toLowerCase().indexOf(letra.toLowerCase()) >= 0) {
        return this.verificarAcertos()
      }
      // erros
      this.erros++
      // enforcado
      if(this.erros === 6) {
        this.etapa = 'enforcado'
      }
    },
    verificarAcertos() {
      let letrasUnicas = [...new Set(this.palavra.split(''))]
      if(letrasUnicas.length === (this.letras.length - this.erros)) {
        this.etapa = 'ganhador'
      }
    },
    jogarNovamente() {
      this.palavra = ''
      this.dica = ''
      this.erros = 0
      this.letras = []
      this.tela = 'inicio'
      this.etapa = 'palavra'
    }
  }
}
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  margin-top: 80px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
