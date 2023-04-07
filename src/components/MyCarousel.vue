<template>
  <v-carousel cycle hide-delimiters>
    <v-carousel-item v-for="(item, index) in items" :key="index">
      <v-card>
        <v-card-title>{{ item.title }}</v-card-title>
        <v-card-text>{{ item.text }}</v-card-text>
        <v-card-actions>
          <v-btn color="primary" dark @click="navigate(item.route)">Learn More</v-btn>
        </v-card-actions>
      </v-card>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  name: "MyCarousel",
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    navigate(route) {
      // Emit an event to notify the parent component to navigate to the specified route
      this.$emit("navigate", route);
    },
  },
};
</script>
