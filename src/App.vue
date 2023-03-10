<template>
  <div id="app">
    <HelloWorld>
      <template v-slot:footer>footer</template>
      <template v-slot:body>body</template>
      <template v-slot:header>header</template>
    </HelloWorld>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",

  components: {
    HelloWorld,
  },

  data() {
    return {
      counter: 0,
      user: {
        person: {
          age: 8,
        },
      },
    };
  },

  watch: {
    counter(newValue) {
      console.log("int_21h-logger-new", newValue);
    },
    user: {
      handler(newValue) {
        console.log("int_21h-logger-newValue", newValue);
      },
      deep: true,
    },
  },

  methods: {
    handleInput(event) {
      this.firstName = event.target.value;
    },
    handleClick(value) {
      console.log(value);
      this.user.person.age++;
    },
  },
};
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
</style>
