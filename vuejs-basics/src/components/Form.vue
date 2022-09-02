<template>
  <div class="binding-form">
    <form action="" method="POST" @submit.prevent="formButtonPressed">
      <fieldset>
        <legend>This is my form:</legend>
        <input
          type="text"
          id="name"
          name="name"
          v-model="name"
          placeholder="Name"
        />
        <br />
        <input
          type="email"
          id="email"
          name="email"
          v-model="email"
          placeholder="Email"
        />
        <br />
        <label for="lang">Favorite Web language:</label>
        <select
          id="lang"
          name="lang"
          v-model="webLanguaje"
          placeholder="Favorite Web language"
        >
          <option value="HTML">HTML</option>
          <option value="CSS">CSS</option>
          <option value="JavaScript">JavaScript</option>
          <option value="Vuejs">Vuejs</option>
        </select>
        <label>Interests:</label>
        <input
          type="checkbox"
          id="angular"
          ref="angular"
          name="interest"
          v-model="interestInAngular"
          value="Angular"
        />
        <label class="light" for="angular">Angular</label>
        <input
          type="checkbox"
          id="react"
          ref="react"
          name="interest"
          v-model="interestInReact"
          value="React"
        />
        <label class="light" for="react">React</label>
        <input
          type="checkbox"
          id="vue"
          ref="vue"
          name="interest"
          v-model="interestInVue"
          value="Vuejs"
        />
        <label class="light" for="vue">Vuejs</label>
      </fieldset>
      <button type="submit">Submit</button>
    </form>
    <div id="bindings">
      <legend>This is the two-way-data-binding result:</legend>
      <p>
        Your name is: <span>{{ name }}</span>
      </p>
      <p>
        Your email is: <span>{{ email }}</span>
      </p>
      <p>
        Your favorite Web language is: <span>{{ webLanguaje }}</span>
      </p>
      <p>
        Your interests are: <span>{{ interestsMessage }}</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Form',
  data() {
    return {
      name: "",
      email: "",
      webLanguaje: "",
      interestInAngular: false,
      interestInReact: false,
      interestInVue: false,
    };
  },
  methods: {
    formButtonPressed() {
      alert("Oops, there was an error connecting to the server 😬");
    },
  },
  computed: {
    interestsMessage() {
      let interests = "";
      if (this.interestInAngular) {
        interests += this.$refs.angular.value;
      }
      if (this.interestInReact) {
        if (interests.length > 0) interests += ", ";
        interests += this.$refs.react.value;
      }
      if (this.interestInVue) {
        if (interests.length > 0) interests += ", ";
        interests += this.$refs.vue.value;
      }
      return interests;
    },
  },
};
</script>

<style scoped>
*,
*:before,
*:after {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

.binding-form {
  font-family: sans-serif;
  max-width: 400px;
  margin: 5px auto;
  padding: 5px 20px;
  background: #f4f7f8;
  border: 2px solid #ccc;
  border-radius: 10px;
}

input[type="text"],
input[type="password"],
input[type="date"],
input[type="datetime"],
input[type="email"],
input[type="number"],
input[type="search"],
input[type="tel"],
input[type="time"],
input[type="url"],
textarea,
select {
  background: rgba(255, 255, 255, 0.1);
  border: none;
  border-radius: 4px;
  font-size: 16px;
  height: 32px;
  margin: 0;
  outline: 0;
  padding: 15px;
  width: 100%;
  background-color: #e8eeef;
  color: #8a97a0;
  -webkit-box-shadow: 0 1px 0 rgba(0, 0, 0, 0.03) inset;
  box-shadow: 0 1px 0 rgba(0, 0, 0, 0.03) inset;
  margin-bottom: 10px;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}
input[type="text"],
input[type="password"],
input[type="email"],
textarea {
  border-top: 2px solid #d2d9dd;
}

input[type="text"]:focus,
input[type="password"]:focus,
input[type="email"]:focus,
input[type="search"]:focus {
  background: #d2d9dd;
  border-radius: 30px;
  border-top: none;
}

textarea:focus {
  background: #d2d9dd;
}

input[type="radio"],
input[type="checkbox"] {
  margin: 0 4px 8px 0;
}

select {
  padding: 6px;
  height: 32px;
  border-radius: 2px;
}

legend {
  font-size: 18px;
  margin-bottom: 10px;
}

label {
  display: block;
  font-weight: 100;
}

label.light {
  font-weight: 300;
  display: inline;
  padding-right: 20px;
}

#bindings {
  margin-top: 10px;
}

span {
  color: crimson;
  background-color: rgba(222, 222, 222, 0.3);
}

button {
  display: block;
  width: 100%;
  margin: 5px 0;
}

@media (max-width: 767px) {
  legend {
    font-size: 16px;
  }
}
</style>