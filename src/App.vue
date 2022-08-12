<template>
  <h1>{{ title }}</h1>
  <p>Welcome</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal" :showModal="showModal">
      <template v-slot:links>
        <a href="/">Sign Up now</a>
        <a href="/">More Info</a>
      </template>
      <h1>Test</h1>
      <p>Unterschrift</p>
      <a href="/">Link</a>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue';
export default {
  name: 'App',
  components: {
    Modal,
  },
  data() {
    return {
      title: 'My first project :)',
      header: 'This is a prop',
      text: 'Im dynamic content',
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
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
button:hover {
  cursor: pointer;
}
</style>
