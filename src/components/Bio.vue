<template>
    <div class="hero flex items-centre justify-between">
        <div class="left flex-1 justify-center">
            <img src="/profile.webp" width="150px" alt="Profile" />
        </div>
        <div class="right flex-1">
            <h6>Caneta Azul</h6>
            <h1>Sou Desenvolvedor <span>Web</span></h1>
            <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
                illum nam nobis, minima laudantium fugit sequi nostrum quod impedit,
                beatae necessitatibus praesentium optio labore nemo!
            </p>
        
            <div>
                <button class="btn-secondary" id="download-cv-button" @click="handleDownloadClick">Dowload do Currículo</button>
            </div>
        </div>
    </div>
</template>

<script setup>

    // Manipulador de evento para o clique no botão
    const handleDownloadClick = () => {
    const pdfUrl = 'src/assets/cv.pdf'; // Caminho para o arquivo PDF
    window.open(pdfUrl, '_blank');
    };

</script>
  
<style scoped>
    .btn-secondary{
        background: transparent;
        color: var(--primary);
        border-color: var(--primary);
        padding: 0.6rem 2rem;
        font-size: 1rem;
        font-weight: 600;
        border: 2px solid var(--primary);
        outline: none;
        cursor: pointer;
        text-transform: uppercase;
        transition: all .2s ease;
    }
    .btn-secondary:hover{
        background: var(--primary);
        color: var(--secondary);
    }

    .hero{
        padding-top: 1rem;
        padding-bottom: 2rem;
    }
    .hero .left img{
        width: 400px;
        margin-left: 20rem;
    }
    .hero .right {
        color: var(--white);
        margin-top: -7rem;
        margin-right: 23rem;
    }
    .hero .right h6{
        font-size: 1.6rem;
        color: var(--primary);
        margin-bottom: 0.5rem;
    }
    .hero .right h1{
        font-size: 4rem;
        font-weight: 100;
        line-height: 1.2;
        margin-bottom: 2rem;
    }
    .hero .right h1 span{
        color: var(--primary);
    }
    .hero .right p{
        line-height: 1.9;
        margin-bottom: 2rem;
    }

</style>