<template>
  <div id="app">
    <b-container>
      <h1 class="title mb-3">簡易チャットアプリ</h1>
      <b-row v-if="user">
        <b-col class="mb-3" cols="12" md="8">
          <chat-logs :messages="messages"></chat-logs>
        </b-col>
        <b-col class="mb-3" cols="12" md="4">
          <chat-form :user="user"></chat-form>
        </b-col>
      </b-row>
      <b-button v-else @click="login" class="login-button" variant="outline-primary">ログイン</b-button>
    </b-container>
  </div>
</template>

<script>
import ChatForm from "./components/ChatForm.vue";
import ChatLogs from "./components/ChatLogs.vue";

export default {
  name: "app",
  components: {
    ChatForm,
    ChatLogs
  },
  data() {
    return {
      user: null,
      messages: [
        {
          userId: "1234",
          userName: "takuya",
          userPhotoURL:
            "https://lh5.googleusercontent.com/-GJQv1cfCfg4/AAAAAAAAAAI/AAAAAAAAAAA/ACHi3rekxUiRbUeFa9MTRgv9MuVw3_F8QA/photo.jpg",
          text:
            "こんばんはああああああああああああああああああああああああああ",
          createdAt: new Date()
        },
        {
          userId: "1234",
          userName: "takuya",
          userPhotoURL:
            "https://lh5.googleusercontent.com/-GJQv1cfCfg4/AAAAAAAAAAI/AAAAAAAAAAA/ACHi3rekxUiRbUeFa9MTRgv9MuVw3_F8QA/photo.jpg",
          text: "こんばんは",
          createdAt: new Date()
        },
        {
          userId: "1234",
          userName: "takuya",
          userPhotoURL:
            "https://lh5.googleusercontent.com/-GJQv1cfCfg4/AAAAAAAAAAI/AAAAAAAAAAA/ACHi3rekxUiRbUeFa9MTRgv9MuVw3_F8QA/photo.jpg",
          text: "こんばんは",
          createdAt: new Date()
        }
      ]
    };
  },
  methods: {
    login() {
      let provider = new this.$firebase.auth.GoogleAuthProvider();
      this.$auth.signInWithPopup(provider).then(() => {});
    }
  },
  mounted() {
    this.$auth.onAuthStateChanged(user => {
      if (user) {
        this.user = user;
      } else {
        this.user = null;
      }
    });
  }
};
</script>

<style lang="scss" scoped>
.title {
  text-align: center;
  font-size: 3rem;
}
.login-button {
  margin: 10px;
  text-align: center;
}
</style>
