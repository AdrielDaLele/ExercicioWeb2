<script setup lang="ts">
import { ref } from "vue";
  
const num1 = ref<number>(0);
const num2 = ref<number>(0);
const result = ref<number | string>(0);
const darkMode = ref(false);

const calculate = (operation: string) => {
  switch(operation) {
    case '+':
      result.value = num1.value + num2.value;
      break;
    case '-':
      result.value = num1.value - num2.value;
      break;
    case '*':
      result.value = num1.value * num2.value;
      break;
    case '/':
      result.value = num2.value !== 0 ? num1.value / num2.value : 'Erro: divisão por zero';
      break;
    case 'sqrt':
      result.value = Math.sqrt(num1.value);
      break;
    default:
      result.value = 'Operação inválida';
  }
};

const checked = ref(false);

const toggleDarkMode = () => {
  darkMode.value = !darkMode.value;
  document.body.classList.toggle('dark-mode');
};
</script>

<template>
  <div class="container">
    <div :class="{ 'dark-mode': darkMode }">
      <div class="input-group">
        <label for="num1">Número 1</label>
        <input type="number" id="num1" v-model="num1">
      </div>
      <div class="input-group">
        <label for="num2">Número 2</label>
        <input type="number" id="num2" v-model="num2">
      </div>

      <div class="operation-buttons">
        <button @click="calculate('+')" class="operation-button">+</button>
        <button @click="calculate('-')" class="operation-button">-</button>
        <button @click="calculate('*')" class="operation-button">*</button>
        <button @click="calculate('/')" class="operation-button">/</button>
        <button @click="calculate('sqrt')" class="operation-button">√</button>
      </div>
      <p :class="{ 'dark-mode-text': darkMode }">Resultado: {{ result }}</p>
    </div>

    <div class="card flex justify-content-center">
      <InputSwitch v-model="checked" @change="toggleDarkMode" />
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.input-group {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 10px;
  padding: 5px 10px;
  background-color: #007bff;
  color: #fff;
  border: 1px solid #000;
  border-radius: 20px;
}

.operation-buttons {
  margin-top: 20px;
}

.operation-button {
  padding: 10px 20px;
  margin: 0 5px;
  font-size: 16px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.dark-mode {
  background-color: #333;
    
}

.dark-mode-text {
  color: #fff;
}

body.dark-mode {
  background-color: #333;
}
</style>
