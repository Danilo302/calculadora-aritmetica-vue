<script setup>
import { reactive } from 'vue';
import FormCalculador from './components/Form-calc.vue'
import Operacao from './components/Operations-calc.vue'

const calc = reactive({
  numero1: 0,
  numero2: 0,
  operacao: '+',
})

function realizarOperacao() {
  switch (calc.operacao) {
    case '+':
      return adicao();
    case '-':
      return subtracao()
    case '*':
      return multiplicacao()
    case '/':
      return divisao()
    default:
      return 'Operação invalida!'
  }
}

const adicao = () => {
  return Number(calc.numero1) + Number(calc.numero2);
}
const subtracao = () => {
  return Number(calc.numero1) - Number(calc.numero2);
}
const multiplicacao = () => {
  return Number(calc.numero1) * Number(calc.numero2);
}
const divisao = () => {
  return Number(calc.numero1) / Number(calc.numero2);
} 
</script>

<template>
  <div class="container">
    <div class="row mt-5">
      <h2 class="text-center text-uppercase">Calculadora Aritmética</h2>
    </div>
    <FormCalculador v-model:numero1="calc.numero1" v-model:numero2="calc.numero2" />
    <Operacao v-model:operacao="calc.operacao" />
    <div class="row justify-content-md-center text-center mt-2">
      <p class="fw-bold">Resultado: {{ realizarOperacao() }}</p>
    </div>
  </div>
</template>

<style scoped></style>
