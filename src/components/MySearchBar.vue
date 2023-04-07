<template>
  <v-card class="search-card" :elevation="elevation">
    <v-card-text>
      <v-form>
        <v-text-field v-model="searchText" label="Search" clearable dense outlined></v-text-field>
        <v-btn color="primary" dark @click="search" :disabled="!searchText">Search</v-btn>
        <v-btn color="primary" dark @click="close">Close</v-btn>
      </v-form>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "MySearchBar",
  props: {
    elevation: {
      type: Number,
      default: 2,
    },
  },
  data() {
    return {
      searchText: "",
    };
  },
  methods: {
    search() {
      // Emit an event to notify the parent component to perform the search with the current search text
      this.$emit("search", this.searchText);
    },
    close() {
      // Emit an event to notify the parent component to close the search bar
      this.$emit("close");
    },
  },
};
</script>

<style>
.search-card {
  position: absolute;
  top: 80px;
  right: 20px;
  width: 300px;
}
</style>
