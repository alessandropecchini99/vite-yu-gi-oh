<script>
import { store } from "../store";
export default {
  data() {
    return {
      store,
    };
  },
  methods: {
    onChange(event) {
      this.$emit(`filter`, event.target.value);
    },
    onReset() {
      this.$emit(`reset`);
    },
  },
};
</script>

<template>
  <div class="searchBar">
    <!-- <input type="text" placeholder="Cerca una carta!" v-model="searchStr" /> -->
    <select
      :value="store.archetypesList.archetype_name"
      @change="onChange"
      v-model="this.store.archetypeStr"
    >
      <option selected value="">Tutte le carte</option>
      <option
        v-for="type in store.archetypesList"
        :key="type.archetype_name"
        :value="type.archetype_name"
      >
        {{ type.archetype_name }}
      </option>
    </select>
    <button @click="onReset">Reset</button>
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
