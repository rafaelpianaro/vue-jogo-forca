<template>
  <div class="forca">
      <!-- <img :src='../assets/' + erros + '.svg' alt=""> -->
      <!-- <img src='../assets/0.svg'> -->
      <!-- <img v-bind:src="'../assets/' + erros + '.svg'" /> -->
      <!-- <img :src="'../assets/' + erros + '.svg'" /> -->
      <!-- <img :src="getImgUrl(pic)" v-bind:alt="pic"> -->
      <img :src="require(`@/assets/${erros}.svg`)" alt class="icon" />
      <!-- <img :src="`https://raw.githubusercontent.com/william-costa/wdev-hangman-game-resources/master/images/hangman/${erros}.svg`" alt=""> -->
  </div>
</template>

<script>
export default {
    name: 'Forca',
    props: {
      erros: Number
    },
}
</script>

<style>
  .forca img {
    /* height: 100%; */
    height: 180px;
  }
</style>