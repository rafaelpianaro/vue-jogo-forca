<template>
  <div class="palavra">
    <div class="palavra-letras">
      <div class="palavra-letra" v-for="(letra,key) in palavra" :key="key">
        {{letra}}
      </div>
    </div>
    <div class="palavra-dica">

    </div>
  </div>
</template>

<script>
export default {
    name: 'Palavra',
    props: {
      palavra: String,
      dica: String,
    },
    data() {

    },
    methods: {
      
    }
}
</script>

<style>
  .palavra {
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    text-align: center;
    align-items: center;
  }
</style>