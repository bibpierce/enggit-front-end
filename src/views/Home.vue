<template>
  <div class="home">
    <template>
      <!-- CAROUSELLLLL -->
      <v-carousel :show-arrows="false" hide-delimiter-background height="900px">
        <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src">
          <div class="carousel-link">
            New Essential Tees<br />
            <span @click="learnMoreRoute">Learn more -></span>
          </div></v-carousel-item
        >
      </v-carousel>
      <!-- CAROUSELLLLL -->
      <!-- 2ND TABS BAR -->
      <v-app-bar flat color="transparent">
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
      <!-- 2ND TABS BAR -->
      <!-- PRODUCT SLIDES -->
      <v-sheet class="mx-auto" max-width="100%">
        <v-slide-group
          v-model="model"
          class="pa-4"
          multiple
          show-arrows
          centered
        >
          <v-slide-item
            v-for="n in 8"
            :key="n"
            v-slot="{ active, toggle }"
            class="mx-5"
          >
            <v-card class="ma-4" height="500px" width="400px" @click="toggle">
              <v-row class="fill-height" align="center" justify="center">
                <v-scale-transition>
                  <div v-if="active">
                    <span color="white" text-align="center">Enggit Tee</span>
                    <br />
                    <v-rating
                      color="warning"
                      hover
                      length="5"
                      readonly
                      size="15"
                    ></v-rating>
                    <span color="white" text-align="center">Price: 500.00</span>
                  </div>
                </v-scale-transition>
              </v-row>
            </v-card>
          </v-slide-item>
        </v-slide-group>
      </v-sheet>
      <!-- PRODUCT SLIDES -->
      <!-- 2nd PRODUCT SLIDES -->
      <v-sheet class="mx-auto" max-width="100%">
        <v-slide-group
          v-model="model"
          class="pa-4"
          multiple
          show-arrows
          centered
        >
          <v-slide-item
            v-for="n in 8"
            :key="n"
            v-slot="{ active, toggle }"
            class="mx-5"
          >
            <v-card
              :color="active ? 'primary' : 'grey lighten-1'"
              class="ma-4"
              height="500px"
              width="400px"
              @click="toggle"
            >
              <v-row class="fill-height" align="center" justify="center">
                <v-scale-transition>
                  <v-icon
                    v-if="active"
                    color="white"
                    size="48"
                    v-text="'mdi-close-circle-outline'"
                  ></v-icon>
                </v-scale-transition>
              </v-row>
            </v-card>
          </v-slide-item>
        </v-slide-group>
      </v-sheet>
      <!-- 2nd PRODUCT SLIDES -->
      <!-- view all button -->
      <div>
        <center>
          <v-btn depressed color="primary">
            Shop All Products
          </v-btn>
        </center>
      </div>
      <!-- view all button -->
    </template>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      model: [],
      gender: [{ title: "Men" }, { title: "Women" }, { title: "Accesories" }],
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
@import url("https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,100,1,0");

.carousel-link {
  padding-top: 35%;
  padding-left: 5%;
}
</style>
