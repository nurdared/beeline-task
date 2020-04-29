<template>
  <section>
    <b-row class="mt-4">
      <b-col sm>
        <b-card>
          <p>
            This is some content within the default block of the
            component. Notice the padding between the card's border and this
          </p>
        </b-card>
      </b-col>
      <b-col sm>
        <b-card>
          <p>
            This is some content within the default block of the
            component. Notice the padding between the card's border and this
          </p>
        </b-card>
      </b-col>
      <b-col sm>
        <b-card>
          <p>
            This is some content within the default block of the
            component. Notice the padding between the card's border and this
          </p>
        </b-card>
      </b-col>
    </b-row>
    <b-row class="mt-4">
      <b-col sm>
        <b-card>
          <p>
            This is some content within the default block of the
            component. Notice the padding between the card's border and this
          </p>
        </b-card>
      </b-col>
      <b-col sm>
        <b-card>
          <p>
            This is some content within the default block of the
            component. Notice the padding between the card's border and this
          </p>
        </b-card>
      </b-col>
      <b-col sm>
        <b-card>
          <p>
            This is some content within the default block of the
            component. Notice the padding between the card's border and this
          </p>
        </b-card>
      </b-col>
    </b-row>
  </section>
</template>


<script>
export default {
  name: "QuoteList",
  props: {
    msg: String
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Arizonia&display=swap");

p {
  font-family: "Arizonia", cursive;
  font-size: 1.3rem;
}
</style>
