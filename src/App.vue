<template>
  <div class="my-app">
    <h1 class="bigger">Witaj w systemie do zapisów na zajęcia</h1>
<!--    <h1>Twój e-mail to: {{ email }}-->
<!--    Dlugosc twojego maila to {{email.length}}</h1>-->
<!--    <div v-if="email.length < 10">Ale masz krótki adres!</div>-->
<!--    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>-->
<!--    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>-->
    <h1 class="smaller">
      Zaloguj się emailem
    <input type="email" v-model="email">


    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
    </h1>
    <div v-if="!email.includes('@')">Niepoprawny mail.</div>

  </div>
</template>

<script>
export default {

  data() {
    return {
      email: '',
      password: ''
    };
  },

  methods: {
    alertMyEmail() {
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

.bigger {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: 40px;
}
.smaller{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: 20px;
}
</style>
