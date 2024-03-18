<template>
  <div class="flex flex-col justify-center gap-5">
    <h1 class="mt-16 text-center text-5xl font-bold text-gray-800">
      Ninja Reaction Timer
    </h1>
    <button @click="start">Play</button>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay);
    },
  },
};
</script>
