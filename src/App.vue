<template>
  <v-app id="inspire">
    <v-app-bar flat>
      <v-app-bar-title>
        <v-icon icon="mdi-circle-slice-4" />

        Enggit Co.
      </v-app-bar-title>

      <v-tabs color="deep-purple accent-4" fixed-tabs centered>
        <v-tab v-for="item in items" :key="item.title" :to="item.to" link>
          {{ item.title }}
        </v-tab>
      </v-tabs>
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
    items: [
      { title: "HOME", icon: "mdi-format-list-checks", to: "/" },
      { title: "PRODUCTS", icon: "mdi-help-box", to: "/products" },
      { title: "ABOUT", icon: "mdi-help-box", to: "/about" }
    ],
    drawer: null
  }),
  components: {
    // search: require("@/components/Utils/Search.vue").default,
    // "live-date-time": require("@/components/Utils/LiveDateTime.vue").default,
    // "add-task": require("@/components/Task/AddTask").default,
    snackbar: require("@/components/Shared/Snackbar.vue").default
  }
  // mounted() {
  //   this.$store.dispatch("getTasks");
  // }
};
</script>

<style scoped>
.tabs {
  font-size: small;
  width: 100px;
}
</style>
