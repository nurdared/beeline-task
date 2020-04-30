<template>
  <section class="mt-3">
    <form action="POST" @submit="addQuote">
      <b-col sm="12" lg="8" class="mx-auto">
        <label for="quote-input" class="font-weight-bold">Quote</label>
        <textarea v-model="text" class="form-control" placeholder="Enter Quote here"></textarea>
      </b-col>
      <b-button type="submit" variant="primary" size="sm" class="mt-2 mx-auto d-flex">Add Quote</b-button>
    </form>
  </section>
</template>

<script>
export default {
  name: "QuoteInput",
  props: {
    msg: String
  },
  data() {
    return {
      text: ""
    };
  },
  methods: {
    addQuote(e) {
      e.preventDefault();
      if (this.text.length === 0) {
        alert("Поле пустое. Пожалуйста введите цитату");
        return;
      }
      const newQuote = this.text;
      this.$emit("add-quote", newQuote);
      this.text = "";
    }
  }
};
</script>
