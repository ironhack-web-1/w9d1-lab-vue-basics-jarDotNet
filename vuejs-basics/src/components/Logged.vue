<template>
  <div id="logged-card">
    <div v-if="userLoggedIn">
      <h2>Hello Welcome!</h2>
      <p>You have sucessfully logged in to your user account!</p>
      <div class="card">
        <img
          src="../../public/img_avatar.png"
          alt="Avatar"
          style="width: 100%"
        />
        <div class="container">
          <h4><b>John Doe</b></h4>
          <p>Architect & Engineer</p>
        </div>
      </div>
    </div>
    <div v-else>
      <h2>Logged out!</h2>
      <p>Please Log In to access your account!</p>
    </div>
    <button @click="userLoggedIn = !userLoggedIn">
      <p v-if="!userLoggedIn">Login</p>
      <p v-else>LogOut</p>
    </button>
  </div>
</template>
    
<script>
export default {
  data() {
    return {
      userLoggedIn: false,
    };
  },
};
</script>

<style scoped>
#logged-card {
  border-radius: 10px;
  background: #f4f7f8;
  border: 2px solid #ccc;
  padding: 20px;
  margin: 15px;
  width: 450px;
  height: 100%;
}

button {
  margin-top: 5px;
}

.card {
  margin: 20px 0;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 40%;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.container {
  padding: 2px 16px;
}

.container > p {
  margin-left: 0;
  margin-block: 5px;
}
</style>