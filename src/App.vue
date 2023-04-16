<template>
  <div class="my-app">
    <h1>Wiataj w systemie zapisów na zajęcia!</h1>
    <div v-if="email">
      Zalogowany jeee {{email}} !!!!
      <a @click="logMeOut">Wyloguj</a>
    </div>
    <div v-else>
<!--      <LoginForm @login="(username) => logMeIn(username)"></LoginForm>-->
      <LoginForm @login="(username) => logMeIn(username)" button-label="Wejdź"></LoginForm>
      <LoginForm @login="(username) => logMeIn(username)" button-label="Wleć"></LoginForm>
      <LoginForm @login="(username) => logMeIn(username)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></LoginForm>
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
  props: {
    hungry: Boolean, // rodzic może ustawić stan hungry dziecka na true lub false
    name: String, // rodzic może ustawić imię dziecka
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
