<script setup>
import { reactive } from 'vue';

const calc = reactive({
  numero1: '',
  numero2: '',
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
    <form>
      <div class="row mt-5 justify-content-md-center">
        <div class="col-2">
          <input v-model="calc.numero1" class="form-control" type="number" required>
        </div>
        <div class="col-2">
          <input v-model="calc.numero2" class="form-control" type="number" required>
        </div>
      </div>
      <div class="row mt-2 justify-content-md-center">
        <div class="col-4">
          <select v-model="calc.operacao" class="form-control text-center btn btn-warning fw-bold">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
          </select>
        </div>
      </div>
    </form>

    <div class="row justify-content-md-center text-center mt-2">
      <p class="fw-bold">Resultado: {{ realizarOperacao() }}</p>
    </div>

  </div>
</template>

<style scoped></style>
