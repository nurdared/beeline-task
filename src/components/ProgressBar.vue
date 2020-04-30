<template>
  <section>
    <h5 class="text-dark">Quotes Added</h5>
    <b-progress :max="max">
      <b-progress-bar :value="value">
        <strong class="text-white">{{ quoteCount }} / {{ max }}</strong>
      </b-progress-bar>
    </b-progress>
  </section>
</template>

<script>
export default {
  name: "ProgressBar",
  props: {
    msg: String,
    quoteCount: Number
  },
  data() {
    return {
      max: 10
    };
  },
  computed: {
    value() {
      return this.quoteCount;
    }
  }
};
</script>
