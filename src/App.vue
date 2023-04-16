<template>
  <div class="my-app">
    <h1>Wiataj w systemie zapisów na zajęcia!</h1>
    <div v-if="email">
      Zalogowany jeee {{email}} !!!!
      <a @click="logMeOut">Wyloguj</a>
    </div>
    <div v-else>
          <LoginForm @login="(username) => logMeIn(username)"></LoginForm>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
   data() {
     return {
       email: '',
       loggedIn: false,
       password: ''
     };
   },
  methods: {
    logMeIn(username) {
      this.email = username;
      // this.loggedIn = true;
    },
    logMeOut(){
      this.email = '';
      // this.loggedIn = false;
    },
    alertMyEmail(){
      alert(this.email);
    }
  },
  components: {
     LoginForm
  }
}

</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
