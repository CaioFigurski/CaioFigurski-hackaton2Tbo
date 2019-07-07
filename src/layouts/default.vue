<template>
  <v-app dark="">
    <v-content>
      <v-container> <nuxt /> </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [
        { icon: "apps", title: "Welcome", to: "/" },
        { icon: "bubble_chart", title: "Inspire", to: "/inspire" },
        { icon: "bubble_chart", title: "Home", to: "/home" }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Dashboard"
    };
  }
};
</script>
