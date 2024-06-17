<script setup lang="ts">

</script>

<template>
    <main class="default-main flex align-items-center justify-content-center">
      <section class="default-container flex flex-column align-items-center justify-content-center">
        <div class="row-default">
            <h1  id="default-title">Lista de Exercicios</h1>
        </div>
        <div class="row-default">
          <Button class="button">
            <NuxtLink to="/exercicio1" class="button">Exercicio 1</NuxtLink>
          </Button>
        </div>
  
        <div class="row-default">
          <Button class="button">
            <NuxtLink to="/exercicio2" class="button">Exercicio 2</NuxtLink>
          </Button>
        </div>
      </section>
    </main>
  </template>
  
  <style scoped lang="scss">
  .default-main {
    width: 100vw;
    height: 100vh;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    align-items: center;
    justify-content: center;
  
    .default-container {
      width: 30vw;
      height: 70vh;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 2rem;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
      border-radius: 10px;
      backdrop-filter: blur(10px);
      background-color: rgba(255, 255, 255, 0.8);
  
      .row-default {
        margin: 1rem 0;
  
        #default-title {
          font-size: 4rem; /* Aumentado o tamanho da fonte */
          color: #da452b !important; /* Amarelo dourado forte */
          text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }
  
        .button {
          width: 250px;
          height: 45px;
          background-color: #da452b;
          color: white;
          border: none;
          border-radius: 5px;
          display: flex;
          align-items: center;
          justify-content: center;
          font-size: 1.2rem; /* Aumentado o tamanho da fonte */
          transition: background-color 0.3s ease;
          text-decoration: none;
  
          &:hover {
            background-color: #da452b;
          }
        }
      }
    }
  }
  </style>
  