<template>
  <div class="home">
    <template>
      <v-carousel :show-arrows="false" hide-delimiter-background height="900px">
        <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src">
          <div class="carousel-link">
            New Essential Tees<br />
            <span @click="learnMoreRoute">Learn more -></span>
          </div></v-carousel-item
        >
      </v-carousel>
      <v-app-bar flat color="">
        <v-tabs centered>
          <v-tab
            v-for="item in gender"
            :key="item.title"
            :to="item.to"
            link
            style=" font-family: 'Quicksand', sans-serif; font-size: 20px"
          >
            {{ item.title }}
          </v-tab>
        </v-tabs>
      </v-app-bar>
    </template>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      gender: [{ title: "Mens" }, { title: "Womens" }, { title: "Objects" }],
      items: [
        {
          src:
            "https://bl6pap003files.storage.live.com/y4mk2WMFNyhoMcsUHiPKwER0_QIKv0HYOxZsYP3G4PtrcBak8UxoF9tZqd8Zx8-N8OKPIYQt8MAh8Y-kpBG8IFJHaSsIgCxU6vizbAsQP83AMiJLC7EwDiBkrHirsz41DRomFUJZnVacgAveDFYA5aTUL0ozlj_BLDjT6TCZzNsk4PwAlWAJPdt9vzrpn6hCf0U?encodeFailures=1&width=962&height=641"
        },
        {
          src:
            "https://bl6pap003files.storage.live.com/y4mtwuePZxVj-io74a7rP1eg2ISaxaRfe_HI6uM2Mtul1CC9m6FOArPyLpESkK91mZCXGD3E7quX4k4SqbA4JiTMyDuueI8kNvnS2JJA0k7TRVWzaTF8oyvP3PS0p-nGEFDgDGSPslb3qFEXjHaBQIXrkEQ8yRry30usC2_T60oOx7EryACZHgb-njpM6FimT-1?encodeFailures=1&width=788&height=525"
        },
        {
          src: "https://cdn.vuetifyjs.com/images/carousel/bird.jpg"
        },
        {
          src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg"
        }
      ]
    };
  },
  methods: {
    learnMoreRoute() {
      this.$router.push(`/About`);
    }
  },

  components: {}
};
</script>

<style>
.carousel-link {
  padding-top: 35%;
  padding-left: 5%;
}
</style>
