<template>
  <div class="jogo">
      <Forca :erros="erros" />
      <Palavra :etapa="etapa" :verificarLetra="verificarLetra" :palavra="palavra" :dica="dica"/>
      <Teclado v-if="etapa === 'jogo'" :jogar="jogar" :letras="letras" :verificarLetra="verificarLetra" />
      <Final v-if="etapa != 'jogo'" :msgFinal="etapa === 'ganhador' ? 'Parabéns!' : 'Perdeu, quem sabe na próxima.'" :etapa="etapa" />
  </div>
</template>

<script>
import Forca from './Forca.vue'
import Palavra from './Palavra.vue'
import Teclado from './Teclado.vue'
import Final from './Final.vue'
export default {
    name: 'Jogo',
    props: {
        erros: Number,
        palavra: String,
        dica: String,
        etapa: String,
        letras: Array,
        jogar: Function,
        verificarLetra: Function,
    },
    data() {

    },
    methods: {

    },
    components: {
        Forca,
        Palavra,
        Teclado,
        Final
    }
}
</script>

<style>
    .jogo {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }
</style>