<template>
  <header>
    <div class="container">
      <nav class="flex items-centre justify-between">
        <div  class="left flex justify-right">
          <div class="logo">
            <img src="/vphome.webp"  width="80px" alt="Logo">
          </div>
          <div>
            <a href="#home">Home</a>
            <a href="#sobre">Sobre</a>
            <a href="#serviços">Serviços</a>
            <a href="https://www.blogger.com/about/?hl=pt-br" target="_blank">Blog</a>
            <a href="https://www.google.com/" target="_blank">Mais</a>
          </div>
        </div>
        <div class="right">
          <button class="btn-primary" @click="toggleContactForm">Contato</button>
        </div>
      </nav>
    </div>
  </header>
  <div v-if="isContactFormVisible" class="contact-overlay">
      <ContactForm />
      <button v-if="isContactFormVisible" class="close-button contact" @click="toggleContactForm">X</button>
  </div>
</template>

<script>
import ContactForm from './ContactForm.vue';

  export default {

    components: {
      ContactForm
    },

    data() {
      return {
        isContactFormVisible: false, // Inicialmente oculto
      };
    },

    methods: {
      toggleContactForm() {
        this.isContactFormVisible = !this.isContactFormVisible; // Alternar o estado
      },
    },

    // Efeito de Rolagem da Página
    mounted() {
        const navigationLinks = document.querySelectorAll('header a');
        const footerLinks = document.querySelectorAll('footer a');
        const internalLinks = document.querySelectorAll('a[href^="#"]'); // Selecionar apenas links internos
        internalLinks.forEach(link => {
            link.addEventListener('click', event => {
                event.preventDefault();
                const targetId = link.getAttribute('href');
                const targetSection = document.querySelector(targetId);
                if (targetSection) {
                    const targetOffset = targetSection.getBoundingClientRect().top + window.pageYOffset;
                    const scrollMargin = parseInt(getComputedStyle(targetSection).scrollMarginTop) || 0;
                    window.scrollTo({
                        top: targetOffset - scrollMargin,
                        behavior: 'smooth'
                    });
                }
            });
        });
    },
};
</script>

<style scoped>

  /* Botão Fechar */
.close-button {
  position: absolute;
  top: 1em;
  right: 1em;
  font-size: 1.5em;
  background: none;
  border: none;
  color: #a8a8a8;
  cursor: pointer;
  margin-top: 11.5em; /* Posicionamento do X */
  margin-right: 28.5em; /* Posicionamento do X */
}

.close-button:hover {
  color: var(--primary);
}

  /* Add styles for the overlay */
  .contact-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5); /* Adjust the transparency as needed */
    z-index: 1000; /* Ensure the overlay is above other content */
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  }
  
  .btn-primary{
    background-color: var(--primary);
    color: var(--secondary);
    margin-top: -15rem;
    padding: 0.6rem 2rem;
    font-size: 1rem;
    font-weight: 600;
    border: 2px solid transparent;
    outline: none;
    cursor: pointer;
    text-transform: uppercase;
    transition: all .2s ease;
  }

  .btn-primary:hover{
    background: transparent;
    border-color: var(--primary);
    color: var(--primary);
  }

  .btn{
    padding: 0.6rem 2rem;
    font-size: 1rem;
    font-weight: 600;
    border: 2px solid transparent;
    outline: none;
    cursor: pointer;
    text-transform: uppercase;
    transition: all .2s ease;
  }

  header{
  background-color: var(--bgDark);
  clip-path: polygon(0 0, 100% 0, 100% 100%, 73% 94%, 0 100%);
  }
  
  header nav .left a{
  color: var(--white);
  text-decoration: none;
  margin-right: 2rem;
  text-transform: uppercase;
  transition: all .2s ease;
  }
  header nav .left a:hover{
  color: var(--primary);
  }
  header nav {
  padding: 1.0rem 0;
  }
  header nav .logo{
  margin-right: 4rem;
  }

</style>
