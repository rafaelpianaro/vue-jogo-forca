<template>
  <div class="final">
      <div :class="`final-texto ${etapa}`">
          {{msgFinal}}
      </div>
      <button class="final-botao">Jogar Novamente</button>
  </div>
</template>

<script>
export default {
    name: 'Final',
    props: {
        etapa: String,
        msgFinal: String
    }
}
</script>

<style>
    .final-texto {
        margin: 20px 0px;
        font-size: 24px;
        font-weight: bold;
    }

    .final-texto.enforcado {
        color: var(--color-text-error)
    }

    .final-texto.ganhador {
        color: var(--color-text-success)
    }
</style>