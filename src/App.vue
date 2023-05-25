<script>
import appLoader from "./components/appLoader.vue";
import appHeader from "./components/appHeader.vue";
import appSearch from "./components/appSearch.vue";
import yugiohList from "./components/yugiohList.vue";

import axios from "axios";
import { store } from "./store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    appLoader,
    appHeader,
    appSearch,
    yugiohList,
  },
  methods: {
    loadApi() {
      axios
        .get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0`)
        .then((response) => (this.store.cardList = response.data.data));
      axios
        .get(`https://db.ygoprodeck.com/api/v7/archetypes.php`)
        .then((response) => (this.store.archetypesList = response.data));
    },
    filtro(type) {
      axios
        .get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?`, {
          params: {
            num: 100,
            offset: 0,
            archetype: this.store.archetypeStr,
          },
        })
        .then((response) => (this.store.cardList = response.data.data));
    },
    resetCard() {
      axios
        .get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0`)
        .then((response) => (this.store.cardList = response.data.data));
      this.store.archetypeStr = ``;
    },
  },
  created() {
    // richiesta api
    this.loadApi();
  },
};
</script>

<template>
  <header>
    <appHeader />
  </header>

  <main>
    <appSearch @filter="filtro" @reset="resetCard" />
    <yugiohList />
    <appLoader v-if="store.cardList.length === 0" />
  </main>
</template>

<style lang="scss">
@use "./assets/general.scss" as *;
</style>
