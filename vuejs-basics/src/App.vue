<template>
  <div id="container">
    <Navbar></Navbar>
    <div class="content">
      <p>2 + 2 = {{ 2 + 2 }}</p>
      <p>Print => {{ sayHello() }}</p>
      <Logged></Logged>
      <Projects></Projects>
      <ColorsWall></ColorsWall>
      <Form></Form>
    </div>
    <Footer></Footer>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
import Logged from "./components/Logged.vue";
import Projects from "./components/Projects.vue";
import ColorsWall from "./components/ColorsWall.vue";
import Form from "./components/Form.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Footer,
    Logged,
    Projects,
    ColorsWall,
    Form,
  },
  methods: {
    sayHello: function (event) {
      return "Hello World!";
    },
  },
};
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
}

#container {
  min-height: 100%;
  position: relative;
}

.content {
  padding-bottom: 120px;
}

.content p {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 0 20px;
}

button {
  margin: 4px;
  border: none;
  border-radius: 5px;
  background-color: rgb(12, 2, 118);
  color: white;
  font-size: 15px;
  padding: 7px 21px;
  font-weight: 500;
  cursor: pointer;
}

button:hover {
  background-color: gray;
}
</style>
