<template>
  <div class="my-3">
    <h4>Quote</h4>
    <textarea
      class="border rounded d-block col-12 p-2"
      v-model="quote"
      @keypress.enter.prevent="addQuote"
      placeholder="Write a new quote..."
      rows="3"
    ></textarea>
    <div class="d-flex justify-content-center">
      <button class="btn btn-primary mt-2" @click="addQuote">Add Quote</button>
    </div>
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
      if (this.quote) {
        this.$emit("quoteAdded", this.quote);
        this.quote = "";
      }
    }
  }
};
</script>
