<template>
  <div class="river">
    <Card v-if="riverCard[0]" :card="riverCard[0]" />
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "River",
  props: ["riverCard"],
  components: { Card },

};
</script>

<style scoped>
.river {
  grid-column: 5 / span 1;
}
</style>
