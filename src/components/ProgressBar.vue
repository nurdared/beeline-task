<template>
  <section>
    <h5 class="text-dark">Quotes Added</h5>
    <b-progress :max="max">
      <b-progress-bar :value="value">
        <strong class="text-white">{{ value }} / {{ max }}</strong>
      </b-progress-bar>
    </b-progress>
  </section>
</template>

<script>
export default {
  name: "ProgressBar",
  props: {
    msg: String
  },
  data() {
    return {
      value: 3,
      max: 10
    };
  }
};
</script>
