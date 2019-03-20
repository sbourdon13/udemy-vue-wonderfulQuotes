<template>
  <div class="container">
    <app-header></app-header>
    <new-quote @quoteAdded="quoteAdded"></new-quote>
    <div class="row">
      <quote-card
        v-for="(quote, index) in quotes"
        :key="quote"
        :quote="quote.text"
        class="col-md-4 col-lg-3 m-3"
        @click.native="deleteCard(index)"
      ></quote-card>
    </div>
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
      quotes: [{ id: 0, text: "I'm a quote!" }, { id: 1, text: "me too!" }],
      newquote: ""
    };
  },
  methods: {
    quoteAdded(newQuote) {
      this.newquote = newQuote;
      const id = this.quotes.length;
      this.quotes.push({
        id: id,
        text: newQuote
      });
    },
    deleteCard(index) {
      this.quotes.splice(index, 1);
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
