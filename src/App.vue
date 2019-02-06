<template>
  <div class="container">
    <app-header></app-header>
    <new-quote @quoteAdded="quoteAdded"></new-quote>
    <quote-card v-for="quote in quotes" :key="quote" :quote="quote.text"></quote-card>
    <app-footer></app-footer>
  </div>
</template>

<script>
import AppHeader from "./layout/Header.vue";
import AppFooter from "./layout/Footer.vue";
import NewQuote from "./components/NewQuote.vue";
import QuoteCard from "./components/QuoteCard.vue";
export default {
  name: "App",
  data() {
    return {
      quotes: [{ id: 1, text: "I'm a quote!" }, { id: 2, text: "me too!" }],
      newquote: ""
    };
  },
  methods: {
    quoteAdded(newQuote) {
      this.newquote = newQuote;
      this.quotes.push({
        id: 5,
        text: newQuote
      });
    }
  },
  components: {
    AppHeader,
    AppFooter,
    NewQuote,
    QuoteCard
  }
};
</script>

<style>
</style>
