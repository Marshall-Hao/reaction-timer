<template>
<div class="flex grid flex-col justify-center">
  <h1 class="text-indigo-700 text-4xl text-center p-10 font-bold">Marshall Reaction Timer</h1>
    <button class="font-bold justify-self-center bg-indigo-500 px-12 py-2 rounded-2xl shadow-lg text-white text-center focus:outline-none" 
  @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay"  class="justify-self-center mt-20"/>
</div>
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: {
    Block,
  },
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    }
  }
}
</script>

