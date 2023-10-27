<template>
    <div>
      <h3>Child Component A</h3>
      <h3>msg from ChildB: {{ message }}</h3>
      <button @click="sendMessageToSibling">Send Message to B</button>
    </div>
  </template>
  
  <script>
  export default {
    props: ['message'],
    methods: {
      sendMessageToSibling() {
        this.$emit('childEvent', "Hello from A");
      }
    }
  }
  </script>