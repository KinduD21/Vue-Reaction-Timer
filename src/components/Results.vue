<template>
  <p class="text-base">Reaction time: {{ score }} ms</p>
</template>

<script>
export default {
  props: ["score"],
};
</script>
