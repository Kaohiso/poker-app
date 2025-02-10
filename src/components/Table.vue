<template>
  <div class="table">
    <div class="community">
      <div class="pot">
        <h1>145 500$</h1>
      </div>
      <div class="community-cards">
        <Flop :flopCards="flop" />
        <Turn :turnCard="turn" />
        <River :riverCard="river" />
      </div>
    </div>
  </div>
</template>

<script>
import Flop from "./Flop.vue";
import Turn from "./Turn.vue";
import River from "./River.vue";

export default {
  name: "Table",
  data() {
    return {
      deck: null,
      communityCards: [], // Cartes au centres de la table
    };
  },
  computed: {
    flop() {
      return this.communityCards.slice(0, 3);
    },
    turn() {
      return this.communityCards.slice(3, 4);
    },
    river() {
      return this.communityCards.slice(4, 5);
    },
  },
  methods: {
    generateDeck() {
      const suits = ["P", "H", "C", "D"]; // Trèfle, Coeur, Carreau, Pique
      const values = [
        "1",
        "2",
        "3",
        "4",
        "5",
        "6",
        "7",
        "8",
        "9",
        "10",
        "V",
        "D",
        "K",
      ];
      let deck = [];

      for (let suit of suits) {
        for (let value of values) {
          deck.push({ f: suit, v: value });
        }
      }
      return deck;
    },
    drawCards() {
      if (this.deck.length === 0) return null;

      const randIndex = Math.floor(Math.random() * this.deck.length);
      return this.deck.splice(randIndex, 1)[0];
    },
    dealCommunityCards() {
      this.communityCards = [];
      for (let i = 0; i < 5; i++) {
        this.communityCards.push(this.drawCards());
      }
    },
  },
  mounted() {
    this.deck = this.generateDeck();
    this.dealCommunityCards();
  },
  components: { Flop, Turn, River },
};
</script>

<style scoped>
.table {
  position: relative;
  width: 70rem;
  height: 33rem;
  background-color: #0a6847;
  border: 20px solid #582900;
  border-radius: 300px;
  position: relative;
  margin: auto;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5), inset 0 0 10px rgba(0, 0, 0, 0.8);
}

.community {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  gap: 10px;
}

.pot {
  background-color: rgba(15, 81, 50, 0.5);
  color: white;
  padding: 10px 20px;
  border-radius: 10px;
  font-weight: bold;
  font-size: 20px;
}

h1 {
  color: white;
  font-size: 16px;
  text-align: center;
  margin: 0;
}

.community-cards {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 1rem;
  justify-content: center;
  align-items: center;
  padding: 10px;
  border-radius: 20px;
  border: 5px solid rgba(15, 81, 50, 0.7);
}
</style>
