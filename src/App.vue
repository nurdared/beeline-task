<template>
  <b-container class="mt-2">
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

const baseUrl = "https://beeline-3fee.restdb.io/rest/db";
const apikey = "apikey=5eaaf516161b39295cdee783";
const sortByDate = "?q={}&sort=_created";

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
    getQuotes() {
      axios
        .get(baseUrl + sortByDate + "&" + apikey)
        .then(response => (this.quotes = response.data))
        .catch(err => console.log(err));
    },

    addQuote(quote) {
      if (this.quotes.length === 10) {
        alert("Для добавления новых цитат удалите одну из добавленных");
        return;
      }
      this.quotes.push({ text: quote });
      axios
        .post(baseUrl + "?" + apikey, {
          text: quote
        })
        .then(response => response.data)
        .then(quote => {
          console.log("Success:", quote);
          this.getQuotes();
        })
        .catch(error => {
          console.error("Error:", error);
        });
    },

    deleteQuote(id) {
      this.quotes = this.quotes.filter(quote => quote._id !== id);
      axios
        .delete(baseUrl + "/" + id + "?" + apikey)
        .catch(e => console.log(e));
    }
  },
  mounted() {
    this.getQuotes();
  }
};
</script>

<style>
</style>
