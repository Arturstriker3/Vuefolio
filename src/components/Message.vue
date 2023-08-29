<template>
    <div class="message-container">
      <p>{{ msg }}</p>
    </div>
  </template>
  
  <script>
    export default {
      name: "Message",
      props: {
        msg: String
      }
    }
  </script>
  
  <style scoped>
    .message-container {
      color: var(--primary);
      background-color: var(--white);
      border: 2px solid var(--secondary);
      border-radius: 5px;
      padding: 10px;
      max-width: 400px;
      margin: 30px auto;
      display: flex;
      justify-content: center; /* Center content horizontally */
      align-items: center; /* Center content vertically */
    }
  </style>