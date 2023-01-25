<template>
  <v-app id="inspire">
    <v-app-bar flat :absolute="true" color="transparent">
      <span class="titulo">
        Enggit Co.
      </span>
      <v-tabs color="white" centered>
        <v-tab
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
          style="color:white; font-family: 'Quicksand', sans-serif; font-size: 20px"
        >
          {{ item.title }}
        </v-tab>
      </v-tabs>
      <v-btn variant="outlined" icon color="white">
        <v-icon>mdi-account</v-icon>
      </v-btn>
      <v-text-field
        v-text-color="white"
        class="text-input-white"
        color="white"
        :loading="loading"
        density="compact"
        variant="solo"
        placeholder="Search"
        append-icon="mdi-magnify"
        single-line
        hide-details
        :style="{ background: white }"
        @click:append="onClick"
      ></v-text-field>
      <v-btn variant="outlined" icon color="white">
        <v-icon>mdi-format-list-bulleted-square</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <router-view></router-view>
      <snackbar />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    loaded: false,
    loading: false,
    items: [
      { title: "HOME", icon: "mdi-format-list-checks", to: "/" },
      { title: "PRODUCTS", icon: "mdi-help-box", to: "/products" },
      { title: "ABOUT", icon: "mdi-help-box", to: "/about" }
    ],
    drawer: null
  }),
  methods: {
    onClick() {
      this.loading = true;

      setTimeout(() => {
        this.loading = false;
        this.loaded = true;
      }, 2000);
    }
  }
};
// components: {
//   // search: require("@/components/Utils/Search.vue").default,
//   // "live-date-time": require("@/components/Utils/LiveDateTime.vue").default,
//   // "add-task": require("@/components/Task/AddTask").default,
//   snackbar: require("@/components/Shared/Snackbar.vue").default
// }
// // mounted() {
// //   this.$store.dispatch("getTasks");
// // }
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Monoton&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Quicksand&display=swap");

.titulo {
  color: aliceblue;
  font-family: "Monoton", cursive;
  overflow: unset;
  font-size: 50px;
  white-space: nowrap;
}
.text-input-white .v-text-field__slot input {
  color: white !important;
}

.text-input-white .v-text-field__slot input::placeholder {
  color: white !important;
}

.text-input-white .v-text-field__slot input::-webkit-search-results-button {
  color: white !important;
}
</style>
