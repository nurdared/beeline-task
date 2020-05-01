<template>
  <b-row>
    <b-col v-for="quote in quotes" :key="quote.id" sm="12" md="6" lg="4" cols="12" class="mt-3">
      <b-card class="fade-in-fwd card-shadow" style="position: relative; ">
        <p>{{quote.text}}</p>
        <div class="h5 mb-0">
          <b-icon
            icon="trash"
            variant="danger"
            style="position: absolute; right:0; bottom: 0; cursor: pointer; margin: 10px;"
            @click="$emit('del-quote', quote._id)"
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

.fade-in-fwd {
  animation: fade-in-fwd 1.5s cubic-bezier(0.39, 0.575, 0.565, 1) both;
}

.fade-out {
  animation: fade-out 0.5s ease-out both;
}

.card-shadow {
  -webkit-box-shadow: 3px 3px 9px -1px rgba(71, 71, 71, 0.86);
  -moz-box-shadow: 3px 3px 9px -1px rgba(71, 71, 71, 0.86);
  box-shadow: 3px 3px 9px -1px rgba(71, 71, 71, 0.86);
}

@keyframes fade-in-fwd {
  0% {
    transform: translateZ(-80px);
    opacity: 0;
  }
  100% {
    transform: translateZ(0);
    opacity: 1;
  }
}

@keyframes fade-out {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
</style>
