<template>
  <v-app-bar :elevation="13">
    <template v-slot:prepend>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
    </template>
    <v-app-bar-title>Secure Blink</v-app-bar-title>

    <template v-slot:append>
      <v-btn>Login</v-btn>

      <v-btn>Free trial</v-btn>

      <v-btn>Demo</v-btn>
    </template>
  </v-app-bar>
</template>

<script>
export default {
  name: "AppBar",

  data: () => ({}),
};

</script>
