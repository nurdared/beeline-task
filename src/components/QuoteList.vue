<template>
  <b-row>
    <b-col v-for="quote in quotes" :key="quote.id" sm="12" md="6" lg="4" cols="12" class="mt-3">
      <b-card>
        <p>{{quote.text}}</p>
        <div class="h5 mb-0" style="position: relative">
          <b-icon
            icon="trash"
            variant="danger"
            style="position: relative; float: right; cursor: pointer"
            @click="$emit('del-quote', quote.id)"
          ></b-icon>
        </div>
      </b-card>
    </b-col>
  </b-row>
</template>


<script>
export default {
  name: "QuoteList",
  props: {
    msg: String,
    quotes: Array
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Arizonia&display=swap");

p {
  font-family: "Arizonia", cursive;
  font-size: 1.3rem;
}

.delete-btn {
  position: relative;
  right: 0;
  bottom: 0;
}
</style>
