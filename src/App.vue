<script setup>
import { ref } from "vue";

// Create an array to store counters for each button
const counts = ref([0, 0, 0, 0]);

// Define a function to increment a specific counter based on index
function increment(index) {
  counts.value[index]++;
}
</script>

<template>
  <div class="flex h-screen items-center justify-center bg-zinc-900">
    <main class="flex w-80 flex-col rounded-lg bg-zinc-800 p-5">
      <ul class="flex flex-col gap-4">
        <!-- Use v-for to loop through the counts array and render buttons -->
        <li v-for="(count, index) in counts" :key="index">
          <button @click="increment(index)"
            class="h-10 w-full rounded-md bg-zinc-700 text-white"
          >
            Count is: {{ count }}
          </button>
        </li>
      </ul>
    </main>
  </div>
</template>
