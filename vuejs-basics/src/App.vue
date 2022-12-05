<template>
  <div id="container">
    <Navbar />
    <div class="content">
      <p>2 + 2 = {{ 2 + 2 }}</p>
      <p>Print => {{ sayHello() }}</p>
      <Logged />
      <Projects />
      <ColorsWall />
      <Form />
      <BiDirectionalForm
        v-model="formValues"
        :names="[
          'name',
          'email',
          'comments',
        ]"
        :hints="[
          'Please enter your name',
          'Please enter your email',
          'Please enter your comments',
        ]"
      />
      <div class="form-results">
        <p>Child-Form results: <span>{{ formValues }}</span></p>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
import Logged from "./components/Logged.vue";
import Projects from "./components/Projects.vue";
import ColorsWall from "./components/ColorsWall.vue";
import Form from "./components/Form.vue";
import BiDirectionalForm from "./components/BiDirectionalForm.vue";

export default {
  name: "App",
  data() {
    return {
      formValues: [],
    };
  },
  components: {
    Navbar,
    Footer,
    Logged,
    Projects,
    ColorsWall,
    Form,
    BiDirectionalForm
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
  margin-top: 60px;
  padding-bottom: 140px;
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

.form-results {
  font-family: "Segoe UI", "Roboto", sans-serif;
  max-width: 400px;
  margin: 5px auto;
  padding: 5px 20px;
  background: #9a8c98;
  border: 2px solid #ccc;
  border-radius: 10px;
}

.form-results > p {
  display: block;
  margin: 0.2rem 0;
  padding-bottom: 10px;
  font-weight: 700;
}

.form-results span {
  color: crimson;
  background-color: rgba(222, 222, 222, 0.3);
}
</style>
