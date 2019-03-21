<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <div class="row justify-content-center">
      <new-quote class="col-md-6" @quoteAdded="quoteAdded"></new-quote>
    </div>
    <div class="row">
      <quote-card
        v-for="(quote, index) in quotes"
        :key="index"
        :quote="quote"
        class="col-md-4 col-xl-3 py-2"
        @click.native="deleteCard(index)"
      ></quote-card>
    </div>
    <div class="mt-2 alert alert-primary">Info: Click on a quote to delete it.</div>
  </div>
</template>

<script>
import AppHeader from "./layout/Header.vue";
import NewQuote from "./components/NewQuote.vue";
import QuoteCard from "./components/QuoteCard.vue";
export default {
  name: "App",
  data() {
    return {
      quotes: ["Just some text to start with something!"],
      maxQuotes: 10
    };
  },
  methods: {
    quoteAdded(newQuote) {
      if (this.quotes.length < this.maxQuotes) {
        this.quotes.push(newQuote);
      } else {
        alert("Too many quotes! Delete some before adding new ones.");
      }
    },
    deleteCard(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    AppHeader,
    NewQuote,
    QuoteCard
  }
};
</script>
