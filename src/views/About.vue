<template>
  <div class="about pa-6">
    <!-- <v-tabs fixed-tabs background-color="indigo" dark>
      <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
        <v-tab :key="item.title">{{ item.title }}</v-tab>
      </v-list-item>
    </v-tabs> -->
    <v-tabs fixed-tabs background-color="indigo" dark>
      <v-tab v-for="item in items" :key="item.title" :to="item.to" link>
        {{ item.title }}
      </v-tab>
    </v-tabs>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      { title: "One", to: "" },
      { title: "Two", to: "" },
      { title: "Three", to: "" },
      { title: "Four", to: "" }
    ],
    drawer: null
  }),
  components: {},
  mounted() {}
};
</script>
