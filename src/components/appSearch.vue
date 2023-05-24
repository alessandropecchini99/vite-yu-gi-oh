<script>
import { store } from "../store";
export default {
  data() {
    return {
      searchStr: ``,
      store,
    };
  },
};
</script>

<template>
  <div class="searchBar">
    <!-- <input type="text" placeholder="Cerca una carta!" v-model="searchStr" /> -->
    <select v-model="searchStr" @change="$emit(`change`, searchStr)">
      <option selected value="">Seleziona tipo</option>
      <option
        v-for="type in store.archetypesList"
        :key="type.archetype_name"
        :value="type.archetype_name"
      >
        {{ type.archetype_name }}
      </option>
    </select>
    <!-- <button @click="$emit(`search`, searchStr)">Cerca</button> -->
    <button @reset="$emit(`reset`)">Reset</button>
  </div>
</template>

<style lang="scss" scoped>
@use "./../assets/variables.scss" as *;

.searchBar {
  @include myContainer;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1em;
  height: 4em;

  select {
    padding: 5px 10px;
    border: 0px;
    border-radius: 5px;
    outline: none;
  }

  select {
    background-color: white;
    cursor: pointer;
  }

  button {
    padding: 5px 15px;
    border: 0px;
    border-radius: 5px;
  }
}
</style>
