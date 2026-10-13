<script setup lang="ts">
import ProjetosSection from '../components/ProjetosSection.vue';
</script>

<template>
  <ProjetosSection />
  <RouterLink class="botao" to="/">⬅️ voltar </RouterLink>
  </template>

  <style scoped>
.botao {
    transition: 0.4s;
    background-color: var(--cor-destaque);
    font: inherit;
    padding: 16px;
    margin: 8px;
    border: none;
    border-radius: 16px;
    text-decoration: none;
    color: var(--cor-texto-botao);
    flex: auto;
}

.botao:hover {
    background-color: #000000;
    color: wheat;

}


  </style>
  