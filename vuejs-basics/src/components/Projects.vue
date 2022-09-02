<template>
  <div class="projects">
    <button @click="getProjects">Get Projects</button>
    <button @click="clearProjects">Clear Projects</button>
    <div v-if="projects.length">
      <div class="wrapper" v-for="project in projects" :key="project.uuid">
        <img
          class="img-project"
          :src="project.image"
          :alt="project.name + 'image'"
        />
        <div class="card">
          <strong>Id: {{ project.uuid }}</strong
          ><br />
          <small>Name: {{ project.name }}</small
          ><br />
          <small>Description: {{ project.description }}</small>
        </div>
      </div>
    </div>
    <p v-if="error" class="alert">{{ error }}</p>
  </div>
</template>

<script>
export default {
  name: 'Projects',
  data() {
    return {
      projects: [],
      error: null,
    };
  },
  methods: {
    async getProjects() {
      try {
        const result = await fetch(
          "https://raw.githubusercontent.com/ironhack-jc/mid-term-api/main/projects"
        );

        if (!result.ok) {
          this.error = "API Error 😬";
          return;
        }
        this.projects = await result.json();
      } catch (error) {
        this.error = "Oops, something went wrong 😬";
      }
    },
    clearProjects() {
      this.projects = [];
      this.error = null;
    },
  },
  mounted() {
    this.getProjects();
    this.loading = true;
  },
};
</script>

<style scoped>
* {
  margin-left: 5px;
}

button {
  margin-left: 15px;
}

.projects {
  border-radius: 10px;
  background: #f4f7f8;
  border: 2px solid #ccc;
  padding: 10px;
  margin: 15px;
  width: 450px;
  height: 100%;
}

.wrapper {
  display: inline-block;
  box-sizing: border-box;
  vertical-align: top;
  width: 200px;
}

.card {
  width: 200px;
  padding: 0 10px;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
  border: 1px solid rgb(245, 209, 100);
  background-color: rgb(243, 232, 198);
}

.img-project {
  width: 200px;
  margin-top: 5px;
}

.alert {
  font-size: 24px;
  color: crimson;
  background-color: rgba(222, 222, 222, 0.3);
}
</style>