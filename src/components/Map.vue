<template>
  <div style="height: 95vh">
    <h3>URL del mapa</h3>
    <v-text-field v-model="url" />
    <l-map
      style="height: 80%; width: 100%"
      :zoom="zoom"
      :center="center"
      @update:zoom="zoomUpdated"
    >
      <l-tile-layer :url="tileUrl" />
    </l-map>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";
import { LMap, LTileLayer } from "vue2-leaflet";
import { LatLng, latLng } from "leaflet";

@Component({
  components: {
    LMap,
    LTileLayer,
  },
})
export default class Map extends Vue {
  //Data
  center: LatLng = latLng(18.664136, -91.83918);
  zoom = 10;
  url = "https://{s}.tile.openstreetmap.org";

  //Methods
  zoomUpdated(zoom: number): void {
    this.zoom = zoom;
  }

  get tileUrl(): string {
    return `${this.url}/{z}/{x}/{y}.png`;
  }
}
</script>

<style></style>
