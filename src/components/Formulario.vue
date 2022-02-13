<template>
  <div class="formulario">
      <div class="formulario-title">{{title}}</div>
      <input type="text" class="formulario-input" v-model="inputValue">
      <button @click="onSubmit" :disable='inputValue.length === 0'>{{button}}</button>
  </div>
</template>

<script>
export default {
    name: 'Formulario',
    props: {
        title: String,
        button: String,
        action: Function
    },
    data() {
        return {
            inputValue: ''
        }
    },
    methods: {
        onSubmit() {
            this.action(this.inputValue)
            this.inputValue = ''
        }
    }
}
</script>

<style>
    .formulario {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        justify-content: center;
        margin-top: 20px;
    }

    .formulario-input {
        padding: 10px 5px;
        border: 0;
        border-radius: 5px;
        margin: 10px 0;
        text-align: center;
        color: var(--color-text-dark);
    }
</style>