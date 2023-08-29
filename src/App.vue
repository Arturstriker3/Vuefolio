<script setup>

import Navbar from './components/Navbar.vue'
import Bio from './components/Bio.vue'
import About from './components/About.vue'
import Services from './components/Services.vue'
import Footer from './components/Footer.vue'

</script>

<template>
  <div>
    <div>
      <Navbar/>
    </div>
    <section id="home" class="sectionBio">
      <div id="biostyle">
        <Bio class="marcomp"/>
      </div>
    </section>
    <section id="sobre" class="sectionAbout">
      <div id="aboutstyle">
        <About class="marcomp"/>
      </div>
    </section>
    <section id="serviços" class="sectionServiços">
    <div id="servicestyle">
      <Services class="marcomp"/>
    </div>
    </section>
    <div id="footerstyle">
      <Footer class="marfooter"/>
    </div>
  </div>
  
</template>

<style scoped>

  /* Rolagem da Pagina */
  .sectionBio {
    scroll-margin-top: 100rem;
  }
  .sectionAbout {
    scroll-margin-top: 5rem;
  }
  .sectionServiços {
    scroll-margin-top: 1rem;
  }

  #biostyle{
    margin-top: 4rem;
  }

  #aboutstyle{
    clip-path: polygon(0 0, 73% 6%, 100% 0, 100% 100%, 0 100%);
    background-color: var(--white);
    display: flex; /* Usando flex para centralizar o componente horizontalmente */
    justify-content: center;
    padding: 20px; /* Adicione espaçamento interno conforme necessário */
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.1); /* Sombra sutil */
  }

  #footerstyle{
    clip-path: polygon(0 0, 73% 6%, 100% 0, 100% 100%, 0 100%);
    display: flex; /* Usando flex para centralizar o componente horizontalmente */
    justify-content: center;
    background-color: var(--white);
  }

  /* Margem entre os componentes */
  .marcomp{
    margin-top: 12rem;
    margin-bottom: 8rem; 
  }

  .marfooter{
    margin-top: 12rem;
  }


</style>
