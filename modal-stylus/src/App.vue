<template>
  <div id="app">
    <div class="example-modal-window">
      <p>ボタンを押すとモーダルウィンドウが開きます</p>
      <button @click="openModal">開く</button>

      <MyModal @closeEvent="closeModal" v-if="modal">
        <p>Vue.js Modal Window!</p>
        <div>
          <input v-model="message">
        </div>

        <!--
        <template slot="footer">
          <button @click="doSend">送信</button>
        </template>
        -->
      </MyModal>
    </div>
  </div>
</template>

<script>
import MyModal from "./components/MyModal.vue";

export default {
  name: "App",
  components: {
    MyModal,
  },
  data() {
    return {
      modal: false,
      message: "",
    }
  },
  methods: {
    openModal() {
      this.modal = true;
    },
    closeModal() {
      this.modal = false;
    },
    doSend() {
      if (this.message.length > 0) {
        alert(this.message);
        this.message = "";
        this.closeModal();
      } else {
        alert("メッセージを入力してください")
      }
    },
  },
};
</script>

<style lang="stylus">
#app
  font-family Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  margin-top 60px
</style>
