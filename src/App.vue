<template>
  <div class="container">
    <app-header></app-header>
    <new-quote></new-quote>
    <quote-card v-for="index in 3" :key="index"></quote-card>
    <app-footer></app-footer>
  </div>
</template>

<script>
import AppHeader from "./layout/Header.vue";
import AppFooter from "./layout/Footer.vue";
import NewQuote from "./components/NewQuote.vue";
import QuoteCard from "./components/QuoteCard.vue";
export default {
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
