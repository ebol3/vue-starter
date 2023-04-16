<template>
  <div class="my-app">
    <h1>Wiataj w systemie zapisów na zajęcia!</h1>
    <div v-if="loggedIn">
      Zalogowany jeee {{email}} !!!!
      <a @click="logMeOut">Wyloguj</a>
    </div>
    <div v-else>
<!--    <h1>Twój e-mail to {{ email }}</h1>-->
          <input type="email" v-model="email">
          <button @click="logMeIn()">Zaloguj się</button>
          <div v-if="!email.includes('@')">Twój e-mail jest nie poprawny </div>
          <div v-else-if="email.length < 10">Twój e-mail jest za krótki bo ma {{email.length}} znaków</div>
          <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
          <div v-else>Twój adres e-mail jest stanowczo za długi bo ma {{email.length}}.</div>
    </div>
  </div>
</template>

<script>
import "milligram";
export default {
   data() {
     return {
       email: 'szyd.luk@gmail.com',
       loggedIn: false,
       password: ''
     };
   },
  methods: {
    logMeIn() {
      this.loggedIn = true;
    },
    logMeOut(){
      this.loggedIn = false;
    },
    alertMyEmail(){
      alert(this.email);
    }
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
