<template>
  <v-app>
    <v-app-bar app color="primary" dark> 
      <v-app-bar-title>Vue-Leaflet - Tiles Visualization</v-app-bar-title>
    </v-app-bar>

    <v-main> 
      <Map />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import Map from "@/components/Map.vue";

export default Vue.extend({
  name: "App",

  components: {
    Map,
  },

  data: () => ({
    //
  }),
});
</script>
