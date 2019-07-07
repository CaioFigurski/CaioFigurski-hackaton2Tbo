<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <div class="text-xs-center">
        <!-- eslint-disable-next-line -->
        
        <!--<avatar size="49">
          <img
            src="~static/lggg.png"
            style="with:100px;"
            alt="Vuetify.js"
            class="mb-5"
          />
        </avatar> -->
      </div>
      <v-card>
        <v-card-title class="headline"> </v-card-title>
        <v-card-text>
          <Login />
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn color="primary" flat nuxt to="/home">Acessar</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import Login from "~/components/Login";

export default {
  components: {
    Login
  },
  data() {
    return {};
  }
};
</script>
