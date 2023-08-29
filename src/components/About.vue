<template>
    <div class="container flex items-centre">
        <div class="left flex-1 justify-right">
            <img src="/profilea.webp" height="400px" alt="profile pic">
        </div>
        <div class="right flex-1">
            <h1>
                Sobre <span>Mim</span>
            </h1>
            <h3>
                Olá! Eu sou Caneta Azul
            </h3>
            <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque adipisci distinctio obcaecati aliquid,
                quia tempora quis optio repudiandae officia earum?
                Lorem ipsum dolor sit amet consectetur, adipisicing elit.
            </p>
            <div class="socials hypersocials">
                <a href="https://linkedin.com/" target="_blank"><img src="/linkedin.webp" class="hlinkedin" width="40px" alt="linkedin"></a>
                <a href="https://github.com/" target="_blank"><img src="/github.webp" class="hgithub" width="40px" alt="github"></a>
                <a href="https://instagram.com" target="_blank"><img src="/instagram.webp" class="hinstagram" width="40px" alt="instagram"></a>
            </div>
        </div>
    </div>
</template>

<script setup>

</script>

<style scoped>
    *{
        background-color: var(--white);
    }

    h1{
        margin-bottom: 1rem;
        font-size: 1.6rem;
        font-weight: 600;
    }

    h1 span{
        color: var(--primary);
    }

    h3{
        font-size: 1rem;
        margin-bottom: 1rem;
        font-weight: 600;
    }

    p{
        font-family: 'Lato', sans-serif;
        color: var(--secondary);
        line-height: 1.9rem;
        margin-bottom: 2rem;
    }

    .socials{
        display: flex;
    }

    .socials a{
        display: flex;
        align-items: center;
        justify-content: center;
        width: 50px;
        margin-right: 0.8rem;
        border-radius: 50%;
    }

    /* Efeitos Hover */

    .hypersocials{
        will-change: filter;
        transition: filter 300ms;
    }

    .hlinkedin:hover {
        filter: drop-shadow(0 0 0.5em #0077b5aa);
        background-color: transparent;
        opacity: 0.85;
    }

    .hgithub:hover {
        filter: drop-shadow(0 0 0.5em #6e5494aa);
        background-color: transparent;
        opacity: 0.85;
    }

    .hinstagram:hover {
        filter: drop-shadow(0 0 0.5em #E1306Caa);
        background-color: transparent;
        opacity: 0.85;
    }
</style>