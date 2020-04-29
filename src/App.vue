<template>
  <b-container>
    <ProgressBar msg="Frontend Dev" />
    <QuoteInput />
    <QuoteList />
  </b-container>
</template>

<script>
import ProgressBar from "./components/ProgressBar.vue";
import QuoteInput from "./components/QuoteInput.vue";
import QuoteList from "./components/QuoteList.vue";

export default {
  name: "App",
  components: {
    ProgressBar,
    QuoteInput,
    QuoteList
  }
};
</script>

<style scoped>
</style>
