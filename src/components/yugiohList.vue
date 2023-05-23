<script>
import yugiohCard from "./yugiohCard.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    yugiohCard,
  },
};
</script>

<template>
  <div class="trovati">Carte trovate: {{ store.cardList.length }}</div>

  <div class="containerCard">
    <yugiohCard
      v-for="card in store.cardList"
      :key="card.id"
      :cardData="card"
    />
  </div>
</template>

<style lang="scss" scoped>
@use "./../assets/variables.scss" as *;

.trovati {
  @include myContainer;
  height: 50px;
  padding-left: 2em;
  background-color: rgb(60, 60, 60);
  color: white;
  display: flex;
  align-items: center;
}

.containerCard {
  @include myContainer;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 2em;

  background-color: white;
  height: fit-content;
  padding: 1.5em;
  margin-bottom: 2em;
}
</style>
