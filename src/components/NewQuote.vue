<template>
  <div class="row">
<form>
  <div class="col-sm-8 col-sm-offset-2  col-xs-12 col-md-6 col-md-offset-3 form-group">
    <label>Quote</label>
    <textarea class="form-control" rows="2" v-model="quote" v-on:keyup="createNewQuote"> </textarea>
  </div>
  <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
    <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
  </div>
</form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        quote: " ",
      }
    },
    methods: {

      createNewQuote (e) {
    if (e.keyCode === 13) {
        this.$emit('QuoteAdded', this.quote);
        this.quote = '';
      }  
      // this.log += e.key;
      
      },
      createNew() {
        this.$emit('QuoteAdded', this.quote);
        this.quote = '';
      }
    }
  }
</script>

<style scoped>
.btn {
  font-family: 'Road Rage', cursive;
  font-size: 2rem;
  padding: 0 1rem;
  background-image: linear-gradient(to bottom,#a0c2d3 0,#4d8aa8 100%);
  border: none;
}
.btn:focus {
  outline: none;
}
</style>