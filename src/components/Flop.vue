<template>
  <div class="flop">
    <Card v-for="(card, index) in flopCards" :key="index" :card="card" />
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Flop",
  props: ["flopCards"],
  components: { Card },
};
</script>

<style scoped>
.flop {
  display: flex;
  gap: 1rem; /* Espacement entre les cartes */
  grid-column: 1 / span 3; /* Prend les 3 premières colonnes */
}
</style>
