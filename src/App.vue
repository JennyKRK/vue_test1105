<template>
  <div class="my-app">
    <h1 class="bigger">Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="email.length>0">Logged in</div>


    <div v-else>
      <LoginForm @login="(username) => logMeIn(username)" button-label="Zaloguj się!"></LoginForm>
    </div>

    <div v-if="email.length>0">Witamy w systemie {{email}}
      <p class="colour" @click="logOut">Wyloguj</p>
        <MeetingPage></MeetingPage>
<!--        meeting page should not be created anew, but be visible/hidden basing on a condition other than email.length-->
    </div>

      

  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import MeetingPage from "@/meetings/MeetingPage.vue";
export default {
  components: {LoginForm, MeetingPage},

  data() {
    return {
      email: '',
      password: '',
    };
  },

  methods: {

    logOut(){
      this.email = '';
      //MeetingPage.style.display = 'none';
    },

    logMeIn(username) {
      this.email = username;
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
.colour{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: blue;

}
</style>
