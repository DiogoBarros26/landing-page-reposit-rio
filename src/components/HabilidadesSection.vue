<script setup lang="ts">
const habilidades = [
    { id: 1, titulo: 'HTML', descricao: 'Estrutura das páginas' },
    { id: 2, titulo: 'CSS', descricao: 'Estilo e layout' },
    { id: 3, titulo: 'Vue', descricao: 'Interfaces reativas' },
    { id: 4, titulo: 'TypeScript', descricao: 'JavaScript com tipos' },
]
</script>

<template>
    <section class="habilidades">
        <h2 class="minhas">Minhas Habilidades</h2>
        <div class="cards">
            <div class="card" v-for="item in habilidades" :key="item.id">

                <h3>{{ item.titulo }}</h3>
                <p>{{ item.descricao }}</p>
            </div>
        </div>

    </section>
</template>

<style scoped>
.habilidades {
    padding: 64px 16px;
    text-align: center;
    /* centraliza o h2 */
}

.cards {
    display: flex;
    gap: 16px;
    justify-content: center;
    flex-wrap: wrap;
}

.card {
    background-color: var(--cor-destaque);
    color: var(--cor-texto-botao);
    padding: 24px;
    border-radius: 16px;
    width: 100%;
    max-width: 260px;
}

.minhas {
    color: var(--cor-titulo);
    
}
</style>