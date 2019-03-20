<template>
  <div>
    <div class="card border rounded p-3">
      <div class="quote">{{ quote }}</div>
    </div>
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
.card:hover {
  background-color: rgb(255, 217, 217);
}

.quote {
  font-family: Arizonia;
  font-size: 18px;
}
</style>
