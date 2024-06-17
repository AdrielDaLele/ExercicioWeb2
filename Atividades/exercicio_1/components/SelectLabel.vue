<script setup lang="ts">
import { ref } from 'vue';

interface Option {
  text: string;
  icon: string;
}

// Inicialize a variável `options` como um ref com um array de objetos Option
const options = ref<Option[]>([
  { text: 'Instagram', icon: 'pi pi-instagram' },
  { text: 'Whatsapp', icon: 'pi pi-whatsapp' },
  { text: 'Facebook', icon: 'pi pi-facebook' },
  { text: 'Twitter', icon: 'pi pi-twitter' },
  { text: 'GitHub', icon: 'pi pi-github' },
]);
// Variáveis reativas
const isOpen = ref(false);
const selectedOption = ref('Select your option');

// Funções
const toggleDropdown = () => {
  isOpen.value = !isOpen.value;
};

const selectOption = (option: Option) => {
  selectedOption.value = option.text;
  isOpen.value = false;
};
</script>

<template>
  <div class="container">
    <h1>Testando o CustomInput</h1>
    <div class="select-menu">
      <div class="select-btn" @click="toggleDropdown">
        <span class="sBtn-text">{{ selectedOption }}</span>
        <i class="pi pi-chevron-down"></i>
      </div>
      <ul class="options" v-if="isOpen">
        <li class="option" v-for="(option, index) in options" :key="index" @click="selectOption(option)">
          <i :class="option.icon"></i>
          <span class="option-text">{{ option.text }}</span>
        </li>
      </ul>
    </div>
    <p>Opção Selecionada: {{ selectedOption }}</p>
  </div>
</template>

<style scoped lang="scss">
body, html {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f0f0f0;
  font-family: Arial, sans-serif;
}

.container {
  text-align: center;
}

.select-menu {
  width: 300px;
  margin: 20px auto;
  position: relative; /* Necessário para posicionar corretamente o dropdown */
}

.select-btn {
  display: flex;
  align-items: center;
  padding: 10px;
  background-color: #fff;
  border: 1px solid #ccc;
  border-radius: 5px;
  cursor: pointer;
}

.select-btn i {
  font-size: 20px;
  margin-left: auto;
}

.options {
  position: absolute;
  top: 100%; /* Ajuste para garantir que o dropdown seja posicionado logo abaixo do botão */
  left: 0;
  width: 100%;
  background-color: #fff;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  list-style: none;
  padding: 0;
  margin: 0;
}

.option {
  display: flex;
  align-items: center;
  padding: 10px;
  cursor: pointer;
}

.option i {
  font-size: 20px;
  margin-right: 10px;
}

.option:hover {
  background-color: #f2f2f2;
}
</style>
