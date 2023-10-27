<template>
    <div>
      <h3>Child Component</h3>
      <h3>From Parent Prop: {{ message }}</h3>
      <button @click="sendMessageToParent">Send Message to Parent</button>
    </div>
  </template>
  
  <script>
  export default {
    props: ['message'],
    methods: {
      sendMessageToParent() {
        this.$emit('childEvent', "Hello from Child");
      }
    }
  }
  </script>