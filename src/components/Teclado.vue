<template>
  <div class="teclado">
      <button class="teclado-botao" v-for="(letra, key) in 'abcdefghijklmnopqrstuvwxyz'" :key="key"
      :disable="verificarLetra(letra)"
      @click="jogar(letra)"
      >
        {{letra}}
      </button>
  </div>
</template>

<script>
export default {
    name: 'Teclado',
    props: {
        letras: Array,
        jogar: Function,
        verificarLetra: Function,
    }
}
</script>

<style>
    .teclado {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        width: 55%;
        margin-top: 20px;
    }

    .teclado-botao {
        margin: 5px;
        text-transform: uppercase;
    }
</style>