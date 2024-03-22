<template>
  <div class="flex flex-col items-center gap-8">
    <h1 class="mt-16 text-center text-5xl font-bold text-gray-800">
      Ninja Reaction Timer
    </h1>
    <button
      class="w-auto rounded-md border-2 border-green-600 px-8 py-1 text-xl disabled:opacity-50"
      @click="start"
      v-bind:disabled="isPlaying"
    >
      {{ buttonText }}
    </button>
    <Block v-if="isPlaying" v-bind:delay="delay" v-on:end="endGame" />
    <Results v-if="showResults" v-bind:score="score" />
  </div>
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";
export default {
  name: "App",
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      buttonText: "Play",
      showResults: false,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.buttonText = "Get ready...";
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.buttonText = "Play";
      this.showResults = true;
    },
  },
};
</script>
