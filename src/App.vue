<template>
  <h1>{{ title }}</h1>
  <Modal header="This is a prop" />
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My first project :)",
    };
  },
};
</script>

<style>
:root {
  --main-color: rgb(20, 146, 219);
  --white: white;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
body {
  background-color: var(--white);
}
h1 {
  color: var(--main-color);
}
</style>
