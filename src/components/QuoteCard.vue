<template>
  <div class="card">
    <p class="quote">{{ quote }}</p>
  </div>
</template>

<script>
export default {
  props: {
    quote: String
  }
};
</script>

<style scoped>
.card {
  border: 1px solid #ccc;
  border-radius: 3px;
}

.quote {
  font-family: Arizonia;
  font-size: 18px;
}
</style>