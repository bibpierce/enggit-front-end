<template>
  <div>
    <div class="account-spacer">
      
    </div>
    <v-row no-gutters>
      <v-col>
        <v-sheet class="">
          <v-parallax
            height="977"
            src="https://i.pinimg.com/564x/5d/e2/9a/5de29a665a19c25a578a895b4e19e602.jpg"
          ></v-parallax>
        </v-sheet>
      </v-col>
      <v-col>
        <v-sheet class="">
          <v-container>
            <v-text-field
              v-model="first"
              color="primary"
              label="First name"
              variant="underlined"
            ></v-text-field>

            <v-text-field
              v-model="last"
              color="primary"
              label="Last name"
              variant="underlined"
            ></v-text-field>

            <v-text-field
              v-model="email"
              color="primary"
              label="Email"
              variant="underlined"
            ></v-text-field>

            <v-text-field
              v-model="password"
              color="primary"
              label="Password"
              placeholder="Enter your password"
              variant="underlined"
            ></v-text-field>

            <v-checkbox
              v-model="terms"
              color="secondary"
              label="I agree to site terms and conditions"
            ></v-checkbox>
          </v-container>
        </v-sheet>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [],
    drawer: null
  }),
  components: {},
  mounted() {}
};
</script>
<style scoped>
.account-spacer {
  background-color: bisque;
  height: 100;
}
</style>
