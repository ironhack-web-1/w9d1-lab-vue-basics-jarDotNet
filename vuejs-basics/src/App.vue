<template>
  <div id="container">
    <Navbar></Navbar>
    <div class="content">
      <p>2 + 2 = {{ 2 + 2 }}</p>
      <p>Print => {{ sayHello() }}</p>
      <Form></Form>
    </div>
    <Footer></Footer>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
import Form from "./components/Form.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Footer,
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
</style>
