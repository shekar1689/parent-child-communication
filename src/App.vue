<template>
  <div id="App">
    <div class="parent-child-cc">
      <h2>Parent Component to see parent-child communication</h2>
      <h2>from Child Message: {{ fromChild }}</h2>
      <ChildComponent :message="message" @childEvent="handleChildEvent" />
    </div>
    <div class="child-child">
    <h2>Parent Component for child-child communication</h2>
    <ChildComponentA :message="messageA" @childEvent="handleChildEventA" />
    <ChildComponentB :message="messageB" @childEvent="handleChildEventB" />
  </div>
  </div>
</template>

<script>
import ChildComponent from './components/ChildComponent.vue';
import ChildComponentA from './components/ChildComponentA.vue';
import ChildComponentB from './components/ChildComponentB.vue';

export default {
  name:"App",
  components: {
    ChildComponent,
    ChildComponentA,
    ChildComponentB
  },
  data() {
    return {
      message: "Hello from Parent",
      messageA: "",
      messageB: "",
      fromChild: ""
    };
  },
  methods: {
    handleChildEvent(childMessage) {
      console.log("Parent received: " + childMessage);
      this.fromChild = childMessage;
    },
    handleChildEventA(childMessage) {
      this.messageB = childMessage;
    },
    handleChildEventB(childMessage) {
      this.messageA = childMessage;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.parent-child-cc{
  border: 2px solid;
  padding: 2%;

}
.child-child{
  border: 2px solid;
  margin-top: 2%;
  padding: 2%;
}
</style>
