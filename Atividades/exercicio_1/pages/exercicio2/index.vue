<script setup lang='ts'>
definePageMeta({
    layout: 'ex2'
})
</script>

<template>
    <header>
    </header>
    <section>
        <div class="button-container">
            <Button class="button">
                <NuxtLink to="/" class="button-link">Home</NuxtLink>
            </Button>
        </div>
        <div class="button-container">
            <Button class="button">
                <NuxtLink to="/exercicio1" class="button-link">Exercicio 1</NuxtLink>
            </Button>
        </div>
        <div class="button-container">
            <Button class="button">
                <NuxtLink to="/exercicio2" class="button-link">Exercicio 2</NuxtLink>
            </Button>
        </div>
    </section>
</template>

<style lang="scss" scoped>
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

section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
}

.button-container {
  margin: 10px 0; /* Espaçamento vertical entre os botões */
  display: flex;
  justify-content: center;
  width: 100%;
}

.button {
  width: 200px; /* Ajustado para ser menor */
  height: 40px; /* Ajustado para ser menor */
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1rem; /* Ajustado para um tamanho de fonte menor */
  transition: background-color 0.3s ease;
}

.button-link {
  color: white;
  text-decoration: none;
}

.button:hover {
  background-color: #007bff ;
}
</style>
