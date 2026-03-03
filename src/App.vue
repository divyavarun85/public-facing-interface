<template>
  <EnvironmentalMap
    data="/chel2022_wgs84.geojson"
    :center="[-98.6, 39.8]"
    :zoom="3.4"
    :style="mapStyle"
    initialFactorId=""
  />
</template>

<script setup>
import EnvironmentalMap from './components/EnvironmentalMap.vue'

const mapStyle = {
  version: 8,
  sources: {
    osm: { type: 'raster', tiles: ['https://tile.openstreetmap.org/{z}/{x}/{y}.png'], tileSize: 256 },
  },
  layers: [{ id: 'osm', type: 'raster', source: 'osm' }],
}
</script>

<style>
* { margin: 0; padding: 0; box-sizing: border-box; }
html, body, #app { width: 100%; height: 100%; }
</style>
