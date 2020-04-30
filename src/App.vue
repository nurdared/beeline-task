<template>
  <b-container>
    <ProgressBar :quoteCount="length" />
    <QuoteInput @add-quote="addQuote" />
    <QuoteList :quotes="quotes" @del-quote="deleteQuote" />
  </b-container>
</template>

<script>
import ProgressBar from "./components/ProgressBar.vue";
import QuoteInput from "./components/QuoteInput.vue";
import QuoteList from "./components/QuoteList.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    ProgressBar,
    QuoteInput,
    QuoteList
  },
  data() {
    return {
      quotes: []
    };
  },
  computed: {
    length() {
      return this.quotes.length;
    }
  },
  methods: {
    getAllQuotes() {
      fetch(
        "https://beeline-3fee.restdb.io/rest/db?apikey=5eaaf516161b39295cdee783"
      )
        .then(res => res.json())
        .then(json => (this.quotes = json.reverse()));
    },
    deleteQuote(id) {
      this.quotes = this.quotes.filter(quote => quote.id !== id);
    },
    addQuote(quote) {
      if (this.quotes.length === 10) {
        alert("Для добавления новых цитат удалите одну из добавленных");
        return;
      }
      axios
        .post(
          "https://beeline-3fee.restdb.io/rest/db?apikey=5eaaf516161b39295cdee783",
          {
            text: quote
          }
        )
        .then(response => response.data)
        .then(quote => {
          console.log("Success:", quote);
          this.getAllQuotes();
        })
        .catch(error => {
          console.error("Error:", error);
        });
    }
  },
  mounted() {
    this.getAllQuotes();
    // axios
    //   .get(
    //     "https://beeline-3fee.restdb.io/rest/db?apikey=5eaaf516161b39295cdee783"
    //   )
    //   .then(response => (this.quotes = response.data))
    //   .catch(err => console.log(err));
  }
};
</script>

<style scoped>
</style>
