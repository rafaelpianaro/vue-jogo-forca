<template>
  <div class="jogo">
      <Forca :erros="erros" />
      <Palavra :etapa="etapa" :verificarLetra="verificarLetra" :palavra="palavra" :dica="dica"/>
      <Teclado :jogar="jogar" :letras="letras" :verificarLetra="verificarLetra" />
  </div>
</template>

<script>
import Forca from './Forca.vue'
import Palavra from './Palavra.vue'
import Teclado from './Teclado.vue'
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
        Teclado
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