<template>
    <div class="container">
        <h1 class="services-head">Serviços</h1>
        <p>Todos seus problemas digitais resolvidos.</p>
        <div class="card-grid">
            <div class="card">
                <img src="/webdesign.webp" alt="WebDesign">
                <h2>Designer Gráfico</h2>
                <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nulla, debitis?</p>
            </div>
            <div class="card">
                <img src="/webdev.webp" alt="WebDev">
                <h2>Desenvolvimento Web</h2>
                <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nulla, debitis?</p>
            </div>
            <div class="card">
                <img src="/blogger.webp" alt="Blogger">
                <h2>Escritor de Conteúdo Digital</h2>
                <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nulla, debitis?</p>
            </div>
        </div>
    </div>
</template>

<script setup>

</script>

<style scoped>

    .services-head{
        color: rgb(10, 9, 9);
        text-align: center;
        margin-bottom: 1rem;
        line-height: 0.5rem;
        color: var(--primary);
    }

    .services-head + p{
        color: var(--white);
        font-family: 'Lato', sans-serif;
        margin-bottom: 1rem;
        text-align: center;
        margin-bottom: 6rem;
        font-weight: 400;
    }

    .card img{
        width: 50px;    
    }

    .card-grid{
        display: grid;
        grid-template-columns: repeat(3,1fr);
        column-gap: 2rem;
    }

    .card-grid .card{
        background: var(--white);
        padding: 3rem 2rem;
        position: relative;
        text-align: center;
        transition: all .2s ease;
    }

    .card-grid .card img{
        position: absolute;
        top: -1.5rem;
        left: 50%;
        transform: translateX(-50%);
        color: var();
    }

    .card-grid .card h2{
        font-weight: 600;
        font-size: 1.2rem;
        margin-bottom: 0.5;
    }

    .card-grid .card p{
        font-family: 'Lato', sans-serif;
        color: var(--secondary);
        line-height: 1.6;
    }

    .card-grid .card:hover{
        background: var(--primary);
    }

    .card-grid .card:hover h2{
        color: var(--white);
    }

    .card-grid .card:hover p{
        color: var(--white);
    }



</style>