<template>
  <section class="chat-form">
    <b-form-textarea v-model="edittingMessage" placeholder="メッセージを入力" rows="3"></b-form-textarea>
    <b-button
      class="chat-form__send-button"
      @click="this.$emit('sendMessage', this.edittingMessage)"
      variant="outline-primary"
    >送信</b-button>
  </section>
</template>

<script>
export default {
  name: "ChatForm",
  data() {
    return {
      edittingMessage: ""
    };
  }
};
</script>

<style scoped>
.chat-form__send-button {
  width: 100%;
}
</style>
