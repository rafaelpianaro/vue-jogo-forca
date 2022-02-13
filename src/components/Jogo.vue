<template>
  <div class="jogo">
      <Forca :erros="erros" />
  </div>
</template>

<script>
import Forca from './Forca.vue'
export default {
    name: 'Jogo',
    props: {
        erros: Number
    },
    data() {

    },
    methods: {

    },
    components: {
        Forca
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