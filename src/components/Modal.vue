<template>
  <div class="backdrop" @click.self="closeModal" :class="{ open: showModal }">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot></slot>
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

<style scoped>
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

.modal.sale {
  background-color: crimson;
  color: white;
}

.modal.sale h1 {
  color: white;
}
</style>
