<script>
export default {
  props: {
    cardData: Object,
  },
};
</script>

<template>
  <div class="card">
    <img :src="cardData.card_images[0].image_url" :alt="cardData.name" />
    <div class="title">{{ cardData.name }}</div>
    <div v-if="cardData.archetype" class="species">
      {{ cardData.archetype }}
    </div>
    <div v-else class="species">none</div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;
  align-items: center;

  width: calc((100% / 5) - 2em);
  height: 100%;
  background-color: #d48f38;
  text-align: center;

  img {
    width: 100%;
    flex-basis: 70%;
  }

  .title {
    flex-basis: 15%;
    margin-top: 0.5em;
    margin-bottom: 0.25em;
    color: white;
  }

  .species {
    flex-basis: 15%;
    margin-top: 0.25em;
    margin-bottom: 0.5em;
  }
}
</style>
