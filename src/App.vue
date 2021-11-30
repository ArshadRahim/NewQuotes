<template>
  <div id="container">
    <h1 class="title text-center">QUOTES APP</h1>
    <app-new-quote @QuoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info"> Info : Click on a qoute to remove it !</div>
      </div>
    </div>
  </div>
</template>
<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
export default {
   components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote
  },
  data: function() {
    return {
      quotes : [ 'this is just a test quote'],
      maxQuotes: 10
    }
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }

}
</script>
<style scoped>
.title, .alert-info {
  font-family: 'Road Rage', cursive;
}
.alert-info {
  font-size: 24px;
  padding: 0;
}
</style>
