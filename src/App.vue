<template>
  <h1>{{ title }}</h1>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "My first project :)",
    };
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
body {
  background-color: rgb(249, 249, 249);
}
h1 {
  color: rgb(20, 146, 219);
}
</style>
