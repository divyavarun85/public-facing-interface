<template>
  <EnvironmentalMap
    :data="dataUrl"
    :center="[-98.6, 39.8]"
    :zoom="3.4"
    :style="mapStyle"
    initialFactorId=""
  />
</template>

<script setup>
import EnvironmentalMap from './components/EnvironmentalMap.vue'

const dataUrl = import.meta.env.BASE_URL + 'chel2022_wgs84.geojson'

const mapStyle = {
  version: 8,
  sources: {
    osm: { type: 'raster', tiles: ['https://tile.openstreetmap.org/{z}/{x}/{y}.png'], tileSize: 256 },
  },
  layers: [{ id: 'osm', type: 'raster', source: 'osm' }],
}
</script>

