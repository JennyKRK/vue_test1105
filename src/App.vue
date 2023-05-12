<template>
    <div class="testApp">
        <p class="firstPart">Hello {{name}} </p>
        <button @click="displayweirdmessages()">weird button</button>
        <label>some weird messages for you</label>
        <ul>
            <li v-for="someMessage in someMessages" :key="someMessage.id">
                {{ someMessage }}
            </li>
        </ul>
        <label>some other weird messages</label>
            <li v-for="todo in todos" :key="todos.id">
                {{ todo.id }} {{todo.text}}
            </li>

        <label>give me your name</label>
        <input type="name" v-model="name">
        <p class="red" v-if="name.length > 10"> Your name is so long {{name}}</p>
        <p v-if="name == 'James' ">James?</p>
        <p v-if="name.charAt(0) == 'A'">Your name starts with A!</p>
        <p v-else-if="name.charAt(0) =='B'">Your name starts with B!</p>
        <p v-else></p>
        <YourMessage @yourText="(something) => allTheThingsYouSaid(something)" buttonLabel="Wejdz"
        additional-label="OOOOOOOOOOOOOOOOO"></YourMessage>
        <p>{{something}}</p>
        <YourAlert @yourReaction="(yourWords) => displayYourReaction(yourWords)" :funny-label="name.length < 10 ? 'Display short alert' : 'Display me'"></YourAlert>
        <YourShortList></YourShortList>


    </div>

</template>

<script>
let id = 0;
import "milligram"
import YourMessage from "@/YourMessage.vue";
import YourAlert from "@/YourAlert.vue";
import YourShortList from "@/YourShortList.vue";

export default {
    components:{YourShortList, YourMessage, YourAlert},
    data(){
        return{
            name: "",
            something: "",
            someMessages: [],
            todos: [
                { id: id++, text: 'Learn HTML'},
                { id: id++, text: 'Learn JavaScript'},
            ],
            newTodo: '',
        }
    },
    methods: {
        allTheThingsYouSaid(newSomething){
            this.something = newSomething;
        },
        displayYourReaction(newReaction){
            alert(newReaction);
        },
        displayweirdmessages(){
            this.someMessages.push("oo")
            this.someMessages.push(this.name);

            this.todos.push({ id: id++, text: this.name, done: false });
            alert(this.someMessages);
        },
    },

}
</script>

<style>
p.firstPart {
    font-size: 2em;
    text-align: center;
    color: blue;
}
p.red{
    color:darkred;
}
p.yourSay{
    color: darkorchid;
}

</style>





<!--<template>-->
<!--  <div class="my-app">-->
<!--    <h1 class="bigger">Witaj w systemie do zapisów na zajęcia</h1>-->
<!--    <div v-if="email.length>0">Logged in</div>-->


<!--    <div v-else>-->
<!--      <LoginForm @login="(username) => logMeIn(username)" button-label="Zaloguj się!"></LoginForm>-->
<!--    </div>-->

<!--    <div v-if="email.length>0">Witamy w systemie {{email}}-->
<!--      <p class="colour" @click="logOut">Wyloguj</p>-->
<!--        <MeetingPage></MeetingPage>-->
<!--&lt;!&ndash;        meeting page should not be created anew, but be visible/hidden basing on a condition other than email.length&ndash;&gt;-->
<!--    </div>-->

<!--      -->

<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--import "milligram";-->
<!--import LoginForm from "./LoginForm";-->
<!--import MeetingPage from "@/meetings/MyItemsPage.vue";-->
<!--export default {-->
<!--  components: {LoginForm, MeetingPage},-->

<!--  data() {-->
<!--    return {-->
<!--      email: '',-->
<!--      password: '',-->
<!--    };-->
<!--  },-->

<!--  methods: {-->

<!--    logOut(){-->
<!--      this.email = '';-->
<!--      //MeetingPage.style.display = 'none';-->
<!--    },-->

<!--    logMeIn(username) {-->
<!--      this.email = username;-->
<!--    }-->
<!--  }-->

<!--}-->

<!--</script>-->

<!--<style>-->
<!--.my-app {-->
<!--  font-family: Avenir, Helvetica, Arial, sans-serif;-->
<!--  text-align: center;-->
<!--  color: #2c3e50;-->
<!--}-->

<!--.bigger {-->
<!--  font-family: Avenir, Helvetica, Arial, sans-serif;-->
<!--  font-size: 40px;-->
<!--}-->
<!--.colour{-->
<!--  font-family: Avenir, Helvetica, Arial, sans-serif;-->
<!--  color: blue;-->

<!--}-->
<!--</style>-->
