<template>
  <div class="container">
    <app-header></app-header>
    <div class="progress">
      <div
        class="progress-bar"
        role="progressbar"
        :style="progressBarStyle"
        :aria-valuenow="progressBarWidth"
        aria-valuemin="0"
        aria-valuemax="100"
      >{{ quotes.length }} / 10</div>
    </div>
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
    <app-footer class="mt-2"></app-footer>
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
      quotes: ["I'm a quote!", "me too!"]
    };
  },
  computed: {
    progressBarWidth() {
      return this.quotes.length * 10;
    },
    progressBarStyle() {
      return { width: `${this.progressBarWidth}%` };
    }
  },
  methods: {
    quoteAdded(newQuote) {
      if (this.quotes.length < 10) {
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
    AppFooter,
    NewQuote,
    QuoteCard
  }
};
</script>

<style>
</style>
