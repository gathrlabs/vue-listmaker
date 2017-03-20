<template>
  <div class="container">
    <app-progress :quoteCount="quotes.length"></app-progress>
    <app-add-quote :quoteCount="quotes.length" @quoteAdded="addQuote"></app-add-quote>
    <app-quotes :quotes="quotes" @removeQuote="removeQuote"></app-quotes>
  </div>
</template>

<script>
import ProgressBar from './components/ProgressBar.vue'
import AddQuote from './components/AddQuote.vue';
import Quotes from './components/Quotes.vue';

export default {
  data: function() {
    return {
      quotes: [],
      maxQuotes: 10,
    }
  },
  components: {
    'app-progress': ProgressBar,
    'app-add-quote': AddQuote,
    'app-quotes': Quotes,
  },
  methods: {
    addQuote(quote) {
      this.quotes.push(quote)
    },
    removeQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
}
</script>

<style lang="sass">
@import '~bulma';
</style>
