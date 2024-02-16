<template>
  <v-app>
    <v-main>
      <AppBar/>
      <NewImage/>
      <!-- <HelloWorld/> -->
    </v-main>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import AppBar from './components/AppBar.vue';
import NewImage from './components/NewImage.vue';
export default {
  name: 'App',

  components: {
    AppBar,
    NewImage,
    // HelloWorld,
  },

  data: () => ({
    //
  }),
}
</script>
