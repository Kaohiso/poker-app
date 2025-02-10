<template>
  <div class="card" :class="['figures-' + card.f, 'values-' + card.v]">
    <h1>{{ card.v }}</h1>
    <div class="figures" :class="card.f"></div>
    <h1>{{ card.v }}</h1>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["card"],
};
</script>

<style scoped>
.card {
  position: relative;
  width: 40px;
  height: 80px;
  background-color: white;
  border-radius: 10px;
  border: 2px solid black;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 5px;
  font-weight: bold;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
}

h1 {
  color: black;
  font-size: 16px;
  text-align: center;
  position: absolute;
  margin: 0;
  &:first-child {
    top: 5px;
    left: 5px;
  }
  &:last-child {
    bottom: 5px;
    right: 5px;
    transform: rotatez(180deg);
  }
}

.figures {
  width: 20px;
  height: 20px;
  background-image: url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/441095/clovers.svg");
  background-size: 40px;
  &.P {
    background-position: 0 0;
  }
  &.D {
    background-position: 20px 0;
  }
  &.C {
    background-position: 20px 20px;
  }
  &.H {
    background-position: 0 20px;
  }
}
</style>
