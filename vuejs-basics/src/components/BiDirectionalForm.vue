<template>
  <form action="" @submit.prevent="$emit('update:modelValue', geInputValues())">
    <fieldset>
      <legend>Bidirectional form:</legend>
      <label id="name-label"
        >Name*
        <input
          type="text"
          id="name"
          ref="name"
          :name="names[0]"
          :placeholder="hints[0]"
          required
        />
      </label>
      <label id="email-label"
        >Email*
        <input
          type="email"
          id="email"
          ref="email"
          :name="names[1]"
          :placeholder="hints[1]"
          required
        />
      </label>
      <label
        >Any Comments
        <textarea
          rows="5"
          cols="30"
          id="comments"
          ref="comments"
          :name="names[2]"
          :placeholder="hints[2]"
        ></textarea>
      </label>

      <button type="submit">Submit</button>
    </fieldset>
  </form>
</template>

<script>
export default {
  name: "BiDirectionalForm",
  props: {
    hints: {
      type: Array,
      default: ["Name", "Email", "Comments"],
    },
    names: {
      type: Array,
      // default: ["user_name", "user_email", "user_comments"],
      required: true
    },
    modelValue: {
      type: Array,
      default: [],
    },
  },
  methods: {
    geInputValues() {
      return [
        this.$refs.name.value,
        this.$refs.email.value,
        this.$refs.comments.value
      ];
    }
  }
};
</script>

<style scoped>
form {
  font-family: "Segoe UI", "Roboto", sans-serif;
  max-width: 400px;
  margin: 15px auto;
  padding: 5px 20px;
  background: #9a8c98;
  border: 2px solid #ccc;
  border-radius: 10px;
}

::placeholder {
  color: #ffffff;
  font-weight: normal;
}

legend {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 10px;
}

label {
  display: block;
  margin: 0.2rem 0;
  padding-bottom: 10px;
}

input,
textarea {
  margin: 10px 0 0 0;
  width: 100%;
  min-height: 2em;
}

input,
textarea {
  background-color: #4a4e69;
  border: 1px solid #4a4e69;
  border-radius: 15px;
  color: #ffffff;
  font-family: Tahoma;
  text-indent: 15px;
}

button {
  display: block;
  width: 100%;
  margin: 5px 0;
}
</style>