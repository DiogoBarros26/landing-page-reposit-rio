<script setup lang="ts">
import { ref, watch } from 'vue';
const modoClaro = ref(localStorage.getItem('tema') === 'claro');
watch(modoClaro, (novoValor) => {
 localStorage.setItem('tema', novoValor ? 'claro' : 'escuro')
})

</script>
<template>

  <div class="pagina" :class="{claro: modoClaro}">
    <RouterView />
    <button class="tema" @click="modoClaro = !modoClaro">{{ modoClaro ? '🌙 Modo escuro' : '☀️ Modo claro'
            }}</button>

  </div>


</template>

<style>
.pagina {
  background: var(--fundo);
  min-height: 100vh;
  --fundo: linear-gradient(135deg, #1b194f 0%, #280137 100%);
  --cor-titulo: White;
  --cor-texto: White;
  --cor-destaque: #fdfbd4;
  --cor-texto-botao: #000000;
  
}
.tema{
  position: fixed;
  background-color: var(--cor-destaque);
  cursor: pointer;
  color: var(--cor-texto-botao);
  top: 16px;
  right: 16px;
  font: inherit;
  border: none;
  padding: 8px;
  border-radius: 16px;
}

.pagina.claro {
  --fundo: linear-gradient(135deg, #f5efe1 0%, #e9dcc3 100%);
  --cor-titulo: #2b1d12;
  --cor-texto: #2b1d12;
  --cor-destaque: #2b1d12;
  --cor-texto-botao: #ffffff;
}
</style>