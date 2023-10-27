<template>
    <div>
      <h3>Child Component B</h3>
      <h3>message from child A: {{ message }}</h3>
      <button @click="sendMessageToSibling">Send Message to A</button>
    </div>
  </template>
  
  <script>
  export default {
    props: ['message'],
    methods: {
      sendMessageToSibling() {
        this.$emit('childEvent', "Hello from B");
      }
    }
  }
  </script>