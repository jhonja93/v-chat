<template>
  <div id="app">
    <div class="v-chat">
      <div v-if="open" class="chat-container open">
        <vcheader v-if="showTitle" />
        <vcmessages />
        <vcinput />
      </div>
      <button @click="open = !open" class="button-launcher">
        <span v-if="!open" class="vc-open-chat-launcher">OPEN CHAT</span>
        <span v-else class="vc-close-chat-launcher">CLOSE CHAT</span>
        <!-- <img v-if="open" src="./assets/close.svg" class="vc-close-launcher" alt="Close chat" />
        <img v-else src="./assets/message.svg" class="vc-open-launcher" alt="Close chat" /> -->
      </button>
    </div>
  </div>
</template>

<script>
import Header from './components/Header';
import Messages from './components/Messages';
import Input from './components/Input';

export default {
  name: 'App',
  data() {
    return {
      open: true,
      showTitle: false
    }
  },
  components: {
    'vcheader' : Header,
    'vcmessages' : Messages,
    'vcinput' : Input
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  background: silver;
  box-shadow: inset -1px -1px #0a0a0a, inset 1px 1px #fff, inset -2px -2px grey, inset 2px 2px #dfdfdf;
}
.v-chat {
  bottom: 0;
  display: flex;
  flex-direction: column;
  margin: 0 20px 20px 0;
  max-width: 370px;
  position: fixed;
  right: 0;
  width: 90vw;
  z-index: 9999;
}
.chat-container {
  /* border-radius: 10px; */
  /* box-shadow: 0 2px 10px 1px #b5b5b5; */
  border: 1px solid #000;
  background-color: #fff;
}
.chat-container.open {
  opacity: 1;
  transform: translateY(0);
  transition: opacity 0.3s ease, transform 0.3s ease;
}
.button-launcher {
  align-self: flex-end;
  border: 0;
  height: 40px;
  margin-top: 10px;
  cursor: pointer;
  width: 150px;
}
.vc-open-chat-launcher {
  /* width: 20px; */
}
.vc-close-chat-launcher {
  /* width: 20px; */
 
}
</style>
