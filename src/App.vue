<template>
  <div id="app">
    <button @click="createBubble">Blow a bubble</button>
    <transition name="bubble">
      <div v-if="bubble" id="bubble">Bubble!</div>
    </transition>
  </div>
</template>

<script>

export default {
  name: 'app',

  data () {
    return {
      msg: "Hello!",
      bubble: false
    }
  },
  methods: {
    createBubble() {
      this.bubble = true;
      setTimeout(() => this.bubble = false, 500)
    }
  }
}
</script>

<style>

#bubble {
  padding: 8px 13px;
  width: max-content;
  background-color: #aaf;
  border-radius: 5px;
}

.bubble-enter {
  opacity: 0;
  transform: translateY(50px);
}

.bubble-enter-active {
  transition: opacity 0.5s, transform 0.5s ease-in
}

.bubble-leave {
  
}

.bubble-leave-active {
  opacity: 0;
  transform: translateY(-50px);
  transition: opacity 0.5s, transform 0.5s ease-out
}


</style>
