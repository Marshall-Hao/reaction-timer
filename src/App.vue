<template>
<div class="flex grid flex-col justify-center">
  <h1 class="text-indigo-700 text-4xl text-center p-10 font-bold">Marshall Reaction Timer</h1>
    <button class="font-bold justify-self-center bg-indigo-500 px-12 py-2 rounded-2xl shadow-lg text-white text-center focus:outline-none" 
  @click="start" :disabled="isPlaying">Play</button>
  <Block @end="endGame" v-if="isPlaying" :delay="delay"  class="justify-self-center mt-20"/>
  <Results class="justify-self-center mt-10 text-2xl font-semibold"  v-if="showResults" :score="score" />
</div>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: {
    Block,
    Results,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    }
  }
}
</script>

