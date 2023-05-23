<script>
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
    appHeader,
    appSearch,
    yugiohList,
  },
  created() {
    // richiesta api
    axios
      .get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0`)
      .then((response) => (this.store.cardList = response.data.data));
  },
};
</script>

<template>
  <header>
    <appHeader />
  </header>

  <main>
    <appSearch />
    <yugiohList />
  </main>
</template>

<style lang="scss">
@use "./assets/general.scss" as *;
</style>
