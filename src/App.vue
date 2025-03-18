<script setup>
import { ref } from 'vue'
const valor = ref(10)

const temperatura_em_celsius = ref(0)
const temperatura_em_farenheit = ref(0)

function converter_para_farenheit() {
  temperatura_em_farenheit.value =  (temperatura_em_celsius.value * 9 ) / 5 + 32
}

function decrementar () {
  valor.value--
}
function duplicar () {
  valor.value = valor.value * 2
}
</script>

<template>
  <h1>Hello World!</h1>
  <button v-on:click="valor++">Incrementar</button>
  <button v-on:click="decrementar">Decrementar</button>
  <button v-on:click="duplicar">Duplicar</button>
  <p>Valor: {{ valor }}</p>
  <h2>Conversor de temperatura</h2>
  <input v-model="temperatura_em_celsius" type="number" step="0.1" />
  <button v-on:click="converter_para_farenheit">Converter</button>
  <p>Temperatura em Farenheit: {{ temperatura_em_farenheit }}</p>
</template>

<style scoped>
  button{
    font-weight: bold;
  }
</style>
