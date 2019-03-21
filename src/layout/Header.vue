<template>
  <div class="mt-4">
    <h1>Quotes Added</h1>
    <div class="progress">
      <div
        class="progress-bar"
        role="progressbar"
        :style="{ width: progressBarWidth + '%' }"
        :aria-valuenow="progressBarWidth"
        aria-valuemin="0"
        aria-valuemax="100"
      >{{ quoteCount }} / {{ maxQuotes }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["quoteCount", "maxQuotes"],
  computed: {
    progressBarWidth() {
      return (this.quoteCount / this.maxQuotes) * 100;
    }
  }
};
</script>
