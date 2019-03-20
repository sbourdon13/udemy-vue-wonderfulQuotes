<template>
  <div>
    <h2>Quote</h2>
    <textarea v-model="quote" @keyup.enter="addQuote" placeholder="Write a new quote..."></textarea>
    <br>
    <button class="btn btn-primary" @click="addQuote">Add Quote</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: ""
    };
  },
  methods: {
    addQuote() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style scoped>
</style>