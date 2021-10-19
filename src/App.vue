<template>
  <div id="app" class="test">
    <Nav></Nav>
    <Content></Content>
    <Nav></Nav>
    <Content></Content>
    <h3>Footer</h3>
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Content from "./components/Content.vue";

export default {
  name: "App",
  components: {
    Nav,
    Content,
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
.test {
  display: flex;
  height: 100vh;
  background-color: red;
  flex-direction: column;
  justify-content: space-between;
}
</style>
