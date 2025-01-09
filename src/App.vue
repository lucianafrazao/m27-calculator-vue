<script setup>
import { reactive } from 'vue';
import Header from './components/Header.vue';
import Calculator from './components/Calculator.vue';

const state = reactive({
  number1: 0,
  number2: 0,
  result: 0,
  operator: 'add',
})

function getNumber1(event) {
  state.number1 = event.target.value;
  if (state.number1 == '') {
    state.number1 = 0;
  }
  state.number1 = parseFloat(state.number1)
  getMath();
}

function getNumber2(event) {
  state.number2 = event.target.value;
  if (state.number2 == '') {
    state.number2 = 0;
  }
  state.number2 = parseFloat(state.number2)
  getMath();
}

function getOperator(event) {
  state.operator = event.target.value;
  getMath();
}

const getMath = () => {
  switch (state.operator) {
    case 'add':
      return state.result = (state.number1 + state.number2);
    case 'subtract':
      return state.result = (state.number1 - state.number2);
    case 'multiply':
      return state.result = (state.number1 * state.number2);
    case 'divide':
      if (state.number2 == 0) {
        return state.result = "Undefined";
      }
      return state.result = (state.number1 / state.number2);
  }
}
</script>

<template>
  <div class="container">
    <Header />
    <Calculator :get-Number-1="getNumber1" :get-Number-2="getNumber2" :result="state.result"
      :get-Operator="getOperator" />
  </div>
</template>

<style scoped></style>
