<template>
  <div id="app">
    <b-container>
      <h1 class="title mb-3">簡易チャットアプリ</h1>
      <b-row>
        <b-col class="mb-3" cols="12" md="8">
          <chat-logs></chat-logs>
        </b-col>
        <b-col class="mb-3" cols="12" md="4">
          <chat-form></chat-form>
        </b-col>
      </b-row>
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
  }
};
</script>

<style scoped>
.title {
  text-align: center;
  font-size: 3rem;
}
</style>
