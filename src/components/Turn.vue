<template>
  <div class="turn">
    <Card v-if="turnCard[0]" :card="turnCard[0]" />
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Turn",
  props: {
    turnCard: Array,
  },
  components: { Card },
};
</script>

<style scoped>
.turn {
  grid-column: 4 / span 1;
}
</style>
