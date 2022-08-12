<template>
  <h1>{{ title }}</h1>
  <p>Welcome</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal" :showModal="showModal">
      <template v-slot:links>
        <a href="/">Sign Up now</a>
        <a href="/">More Info</a>
      </template>
      <h1>Test</h1>
      <p>Unterschrift</p>
      <a href="/">Link in normal slot</a>
    </Modal>
  </teleport>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>{{ title }}</h1>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal</button>
  <br />
  <br />
  <button @click="toggleModalTwo">Open Modal Two</button>
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
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
:root {
  --main-color: rgb(20, 146, 219);
  --white: white;
}
#app,
.modals {
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
