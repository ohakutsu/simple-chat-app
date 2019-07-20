<template>
  <div id="app">
    <b-container>
      <h1 class="title">簡易チャットアプリ</h1>
      <chat-form></chat-form>
    </b-container>
  </div>
</template>

<script>
import ChatForm from "./components/ChatForm.vue";

export default {
  name: "app",
  components: {
    ChatForm
  }
};
</script>

<style scoped>
.title {
  text-align: center;
  font-size: 3rem;
}
</style>
