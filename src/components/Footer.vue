<template>
    <footer>
        <div class="logo-container">
            <a href="https://vitejs.dev" target="_blank">
                <img src="/vite.svg" width="50px" class="logo-vite" alt="Vite logo" />
            </a>
            <a href="https://vuejs.org/" target="_blank">
                <img src="/vue.svg" width="50px" class="logo-vue" alt="Vue logo" />
            </a>
        </div>
        <div class="link_menu">
            <a href="#home">Home</a>
            <a href="#sobre">Sobre</a>
            <a href="#serviços">Serviços</a>
            <a href="https://www.blogger.com/about/?hl=pt-br" target="_blank">Blog</a>
            <a href="https://www.google.com/" target="_blank">Mais</a>
        </div>
        <p>&copy;{{ new Date().getFullYear() }} Vuefólio | Todos os Direitos Reservados</p>
    </footer>
</template>

<script setup>
    
</script>

<style scoped>

    /* Estilização Logos Vue e Vite */
    .logo-container {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1.5rem; /* Espaçamento entre os logos */
        margin: 2rem 0; /* Adicione um espaçamento vertical */
    }

    .logo-vue .logo-vite{
        height: auto;
        max-width: 100%; /* Garante que as imagens não excedam o tamanho do container */
        will-change: filter;
        transition: filter 300ms;
    }

    .logo-vite:hover {
        filter: drop-shadow(0 0 2em #646cffaa);
        background-color: transparent;
        opacity: 0.85;
    }
    .logo-vue:hover {
        filter: drop-shadow(0 0 2em #42b883aa);
        background-color: transparent;
        opacity: 0.85;
    }

    footer{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Poppins', sans-serif;

        position: relative;
        width: 100%;
        background: var(--white);
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .link_menu {
        color: var(--black);
        text-decoration: none;
        margin: 0.1rem 0; /* Adicionar espaçamento vertical entre os links */
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .link_menu a {
        margin: 0 1rem; /* Adicionar espaçamento horizontal entre os links */
        text-decoration: none; /* Remover o sublinhado dos links */
        color: var(--black);
        transition: color 0.2s ease, text-shadow 0.3s ease; /* Adicionar transição para o text-shadow */
    }

    .link_menu a:hover {
        color: var(--primary);
        opacity: 1;
        text-shadow: 0 0 5px rgba(0, 0, 0, 0.3); /* Adicionar sombra para criar o efeito de desfoque */
        
    }

    p{
        color: var(--black);
        margin: 15px 0 10px 0;
        font-size: 1rem;
        font-weight: 1000;
    }

</style>