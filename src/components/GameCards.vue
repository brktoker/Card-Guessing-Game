<template>
  <div class="game-area">
    <h1 class="title">Where is The Cat <strong>?</strong></h1>
    <h4 class="description">Find the cat among the cards</h4>
    <div class="container">
      <transition-group
        class="cart-container animate__animated animate__jackInTheBox"
        appear
        name="flip"
        mode="out-in"
      >
        <app-card
          :class="{ shadow: selectCard == card.id }"
          @click.native="selectCard = card.id"
          v-for="card in cards"
          :key="card.id"
          :card="card"
        >
        </app-card>
      </transition-group>
    </div>
    <div class="container">
      <transition
        leave-class=""
        leave-active-class="animate__animated animate__backInUp"
        mode="out-in"
      >
        <component
          @click.native="showCard(answer)"
          :card="answer"
          :is="cardComponent"
        >
        </component>
      </transition>
    </div>
  </div>
</template>

<script>
import Card from "./Card";
import DefaultCard from "./DefaultCard";

export default {
  components: {
    appCard: Card,
    appDefaultCard: DefaultCard,
  },
  data() {
    return {
      selectCard: null,
      answer: {},
      cardComponent: "appDefaultCard",
      cards: [
        { id: 1, component: "appCard", image: "/src/assets/card-1.jpg" },
        { id: 2, component: "appCard", image: "/src/assets/card-2.jpg" },
        { id: 3, component: "appCard", image: "/src/assets/card-3.jpg" },
        { id: 4, component: "appCard", image: "/src/assets/card-4.jpg" },
        { id: 5, component: "appCard", image: "/src/assets/card-5.jpg" },
      ],
    };
  },
  created() {
    let answer = Math.ceil(Math.random() * this.cards.length);
    this.answer = this.cards[answer - 1];
  },
  methods: {
    showCard(answer) {
      this.cardComponent = answer.component;
    },
  },
};
</script>

<style scoped>
.title {
  text-align: center;
  color: rebeccapurple;
}
.title strong {
  color: darkred;
}
.description {
  text-align: center;
  color: forestgreen;
  transition: text-shadow 0.5s;
}
.description:hover {
  text-shadow: 0px 5px 24px #666;
  transition: text-shadow 0.5s;
}
.container,
.cart-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 50px;
}
.shadow {
  box-shadow: 0px 5px 96px green !important;
  transition: box-shadow;
}
</style>