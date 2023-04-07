<template>
  <v-footer color="primary" app>
    <v-card>
      <v-card-title class="text-center">Contact Us</v-card-title>
      <v-card-text>
        <p>Email: contact@yourwebsite.com</p>
        <p>Phone: 555-555-5555</p>
      </v-card-text>
      <v-card-actions>
        <v-btn color="primary" text href="#">Privacy Policy</v-btn>
        <v-btn color="primary" text href="#">Terms of Use</v-btn>
      </v-card-actions>
      <v-card-actions>
        <v-btn color="primary" text href="#">Facebook</v-btn>
        <v-btn color="primary" text href="#">Twitter</v-btn>
        <v-btn color="primary" text href="#">Instagram</v-btn>
      </v-card-actions>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: "MyFooter",
};
</script>

<style scoped>
/* add any custom styles for the footer here */
</style>
