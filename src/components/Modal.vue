<template>
  <div class="backdrop" @click.self="closeModal" :class="{ open: showModal }">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>Default content only shown if nothing passed</slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: ['theme', 'showModal'],
  methods: {
    closeModal() {
      this.$emit('close');
    },
  },
};
</script>

<style>
.backdrop {
  top: 0;
  position: fixed;
  background-color: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

.backdrop.open {
  cursor: pointer;
}
.backdrop.open .modal {
  cursor: auto;
}
.modal {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background-color: white;
  border-radius: 10px;
}

.modal .actions {
  text-align: center;
  margin: 30px 0px 10px 0px;
  color: #333;
}

.modal .actions a {
  color: #eee;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
  transition: all 0.3s ease-in-out;
}

.modal .actions a:hover {
  color: rgb(33, 33, 33);
  transition: all 0.3s ease-in-out;
  border: 1px solid rgb(33, 33, 33);
}

.modal.sale {
  background-color: crimson;
  color: white;
}

.modal.sale h1 {
  color: white;
}
</style>
