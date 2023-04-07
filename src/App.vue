<template>
  <v-app>
    <v-app-bar app>
      <v-navigation-drawer app>
        <v-list>
          <v-list-tile>
            <v-list-tile-title>Home</v-list-tile-title>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-title>About</v-list-tile-title>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-title>Contact</v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
      <v-toolbar-title>My Website</v-toolbar-title>
    </v-app-bar>

    <v-container>
      <v-toolbar>
        <v-text-field label="Search" prepend-icon="mdi-magnify"></v-text-field>
      </v-toolbar>

      <v-carousel>
        <v-carousel-item v-for="stock in stocks" :key="stock.id">
          <img :src="stock.image" alt="Stock">
        </v-carousel-item>
      </v-carousel>

      <v-card>
        <v-card-title>{{ randomStock }}</v-card-title>
        <v-card-text>
          <v-line-chart :data="chartData"></v-line-chart>
        </v-card-text>
      </v-card>
    </v-container>

    <v-footer>
      <v-layout>
        <v-flex>
          <v-btn icon>
            <v-icon> mdi-facebook</v-icon>
          </v-btn>
          <v-btn icon>
            <v-icon>mdi-twitter</v-icon>
          </v-btn>
          <v-btn icon>
            <v-icon>mdi-linkedin</v-icon>
          </v-btn>
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Contact Us</v-card-title>
            <v-card-text>
              <p>Address: 123 Main St</p>
              <p>Phone: 555-1234</p>
              <p>Email: info@mywebsite.com</p>
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
import MyMenu from "./components/MyMenu.vue";
import MySearchBar from "./components/MySearchBar.vue";
import MyCarousel from "./components/MyCarousel.vue";
import MyFooter from "./components/MyFooter.vue";

export default {
  name: "App",
  components: {
    MyMenu,
    MySearchBar,
    MyCarousel,
    MyFooter,
  },
  data() {
    return {
      stocks: [
        { id: 1, image: "stock1.jpg" },
        { id: 2, image: "stock2.jpg" },
        { id: 3, image: "stock3.jpg" },
      ],
      randomStock: "AAPL",
      chartData: {
        labels: ["January", "February", "March", "April", "May", "June", "July"],
        datasets: [
          {
            label: "Stock Price",
            backgroundColor: "rgba(255, 99, 132, 0.2)",
            borderColor: "rgba(255, 99, 132, 1)",
            borderWidth: 1,
            data: [65, 59, 80, 81, 56, 55, 40],
          },
        ],
      },
    };
  },
};
</script>

