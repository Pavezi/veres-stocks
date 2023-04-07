<template>
  <v-navigation-drawer app right v-model="drawer">
    <v-list dense>
      <v-list-item v-for="(item, index) in items" :key="index" @click="navigate(item.route)">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
  <v-app-bar app color="primary" dark>
    <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    <v-toolbar-title>{{ title }}</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn icon @click="openSearch">
      <v-icon>mdi-magnify</v-icon>
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: "MyMenu",
  props: {
    title: {
      type: String,
      default: "My Website",
    },
    items: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      drawer: false,
    };
  },
  methods: {
    navigate(route) {
      this.$router.push(route);
      this.drawer = false;
    },
    openSearch() {
      // Emit an event to notify the parent component to open the search bar
      this.$emit("openSearch");
    },
  },
};
</script>
