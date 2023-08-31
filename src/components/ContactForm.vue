<template>
    <div class="elegant-contact-form">
      <h1>Contate-Me</h1>
      <form class="cf" @submit.prevent="handleSubmit">
        <div class="half left cf">
          <input v-model="name" type="text" placeholder="Name">
          <input v-model="email" type="email" placeholder="Email address">
          <input v-model="subject" type="text" placeholder="Subject">
        </div>
        <div class="half right cf">
          <textarea v-model="message" placeholder="Message"></textarea>
        </div>
        <input type="submit" value="Submit">
      </form>
      <Message v-if="showMsg" :msg="msg" />
    </div>
</template>

<script setup>
import { ref } from 'vue';
import Message from './Message.vue';
import emailjs from 'emailjs-com';

const name = ref('');
const email = ref('');
const subject = ref('');
const message = ref('');
const msg = ref('');
const showMsg = ref(false);

const handleSubmit = () => {
  const templateParams = {
    subject: subject.value,
    name: name.value,
    email: email.value,
    message: message.value,
  };

  emailjs.send(
    'gmail_Message',
    '####',
    templateParams,
    '####'
  )
    .then(response => {
      // Display a success message or perform other actions
      msg.value = 'Mensagem Enviada!';
      showMsg.value = true;
      setTimeout(() => {
        msg.value = '';
        showMsg.value = false;
      }, 3000);
    })
    .catch(error => {
      // Handle error cases
      console.error(error);
      msg.value = 'Erro no Envio!';
      showMsg.value = true;
    });
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Merriweather');


.elegant-contact-form {
    background: #f1f1f1;
    font-family: 'Merriweather', sans-serif;
    padding: 1em;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}   

h1 {
  text-align: center;
  color: #a8a8a8;
  text-shadow: 1px 1px 0 rgba(255, 255, 255, 1);
}

form {
  max-width: 600px;
  text-align: center;
  margin: 20px auto;
}

input, textarea {
  border: 0;
  outline: 0;
  padding: 1em;
  border-radius: 8px;
  display: block;
  width: 100%;
  margin-top: 1em;
  font-family: 'Merriweather', sans-serif;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
  resize: none;
}

input[type="submit"] {
  color: white; 
  background: var(--primary);
  cursor: pointer;
}

input[type="submit"]:hover {
  box-shadow: 0 1px 1px 1px rgba(170, 170, 170, 0.6);
}

textarea {
  height: 126px;
}

.half {
  float: left;
  width: 48%;
  margin-bottom: 1em;
}

.right {
  width: 50%;
}

.left {
  margin-right: 2%; 
}

@media (max-width: 480px) {
  .half {
    width: 100%; 
    float: none;
    margin-bottom: 0; 
  }
}

/* Clearfix */
.cf:before,
.cf:after {
  content: " "; /* 1 */
  display: table; /* 2 */
}

.cf:after {
  clear: both;
}
</style>
