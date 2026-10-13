<script setup lang="ts">
import { ref } from 'vue'

const mostrar = ref(false)
defineProps<{
    titulo: string
    subtitulo: string
}>()
</script>

<template>
    <section class="hero">
        <h1 class="titulo">
            {{ titulo }}
        </h1>
        <p class="sub-titulo">
            {{ subtitulo }}
        </p>
        <div class="acoes">
            <RouterLink class="botao" to="/projetos">Ver Portfólio</RouterLink>
            <button class="botao" @click="mostrar = !mostrar">{{ mostrar ? 'Mostrar menos' : 'Saiba mais sobre mim'
            }}</button>
        </div>
        <p class="sobre" v-if="mostrar">Meu nome é Diogo Augusto Martins de Barros e sou um cara curioso: gosto de
            encontrar problemas e entender de onde eles vêm. Estudo Análise e Desenvolvimento de Sistemas na Cruzeiro do
            Sul e busco oportunidades como QA ou Desenvolvedor Júnior.</p>

    </section>


</template>

<style scoped>
.hero {
    padding: 0px 16px;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    min-height: 100vh;

}

.titulo {
    color: var(--cor-titulo);
    font-size: clamp(19px, 6vw, 75px);
}

.sub-titulo {
    color: var(--cor-texto);
    font-size: 16px;
}

.acoes {
    gap: 16px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

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

.sobre {
    color: var(--cor-texto);
    font-size: 16px;
    max-width: 600px;
    text-align: center;
}
</style>