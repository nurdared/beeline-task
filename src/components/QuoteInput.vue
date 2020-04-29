<template>
  <section class="mt-3">
    <b-col sm="6" lg="8" class="mx-auto">
      <label for="quote-input" class="font-weight-bold">Quote</label>
      <b-form-textarea id="quote-input" placeholder="Enter Quote here"></b-form-textarea>
    </b-col>
    <b-button variant="primary" size="sm" class="mt-2 mx-auto d-flex">Add Quote</b-button>
  </section>
</template>

<script>
export default {
  name: "QuoteInput",
  props: {
    msg: String
  }
};
</script>
