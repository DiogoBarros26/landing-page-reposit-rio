<script setup lang="ts">
interface Projeto {
    id: number
    nome: string
    descricao: string
    tecnologias: string[]
    link: string
}
const projetos: Projeto[] = [
    { id: 1, nome: 'Landing page', descricao: 'Meu portfólio pessoal, feito para aprender Vue na prática, com tema claro e escuro que fica salvo no navegador.', tecnologias: ['Vue', 'TypeScript', 'CSS', 'Vite'], link: '#' },
    { id: 2, nome: 'fabula-fichas', descricao: 'Site em produção onde meu grupo de RPG cria e guarda fichas de Fabula Ultima, com login, campanhas por código de convite e cálculos automáticos.', tecnologias: ['Next.js', 'React', 'TypeScript', 'PostgreSQL', 'Tailwind CSS'], link: 'https://fabula-fichas.vercel.app' },
    { id: 3, nome: 'AgendaCRUD', descricao: 'Agenda de contatos com cadastro, edição e exclusão, desenvolvida como teste técnico para um processo seletivo de estágio.', tecnologias: ['C#', 'ASP.NET Core', 'Vue', 'SQL Server', 'Docker'], link: 'https://github.com/DiogoBarros26/meuCRUD' },
];
</script>

<template>
    <section class="projetos">
        <h2 class="titulo-projetos">Meus Projetos</h2>
        <div class="cards">
            <div class="card" v-for="projeto in projetos" :key="projeto.id">
                <h3>{{ projeto.nome }}</h3>
                <p>{{ projeto.descricao }}</p>
                <ul>
                    <li v-for="tec in projeto.tecnologias" :key="tec">{{ tec }}</li>
                </ul>
                <a :href="projeto.link" target="_blank" rel="noopener noreferrer">Ver Projeto</a>
            </div>
        </div>
    </section>

</template>

<style scoped>
.projetos {
    padding: 16px;
    color: var(--cor-texto);
    text-align: center;

}

.titulo-projetos {
    color: var(--cor-titulo);

}

.cards{
    display: flex;
    gap: 16px;
    justify-content: center;
    flex-wrap: wrap;
    
}

.card{
color: var(--cor-texto-botao);
text-align: left;
background-color: var(--cor-destaque);
padding: 24px;
border-radius: 16px;
width: 100%;
max-width: 260px;
}

.card a{
    color: inherit;
    font-weight: bold;
}
</style>