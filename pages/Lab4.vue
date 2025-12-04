<template>
  <div style="height: 100vh; width: 100vw;" class="w-screen h-screen">
    <LMap
      :zoom="12"
      :center="petropavl"
      :use-global-leaflet="false"
      style="height: 100%; width: 100%;"
    >
      <LTileLayer
        url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
        attribution="&copy; OpenStreetMap contributors"
      />

      <LMarker :lat-lng="petropavl" :draggable="false">
        <LTooltip permanent direction="top">
          Petropavl (NKR)
        </LTooltip>

        <LPopup>
          <strong>Petropavl</strong><br />
          North Kazakhstan Region
        </LPopup>
      </LMarker>
      <LMarker
        v-for="(lake,i) in lakes"
        :key="i"
        :lat-lng="[lake.lat, lake.lng]"
        :draggable="false"
      >
        <LTooltip permanent direction="top">{{ lake.name }}</LTooltip>
        <LPopup>
          <strong>{{ lake.name }}</strong><br />
          transparency information: {{ lake.level }}
        </LPopup>
      </LMarker>
    </LMap>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue"
import { LMap, LTileLayer, LMarker, LTooltip, LPopup } from "@vue-leaflet/vue-leaflet"
import 'leaflet/dist/leaflet.css'

type LatLngTuplle = [number, number]

interface Lake{
  name: string 
  lat: number
  lng: number
  level: number
}
const petropavl = ref<LatLngTuplle>([54.88, 69.16])

const lakes = ref<Lake[]>([
  {name: 'Pestroye Lake', lat: 54.836699, lng: 69.111328, level:1.3},
  {name: 'Beloe Lake', lat: 54.927154, lng: 69.254322, level:1.3},
  {name: 'Gorkoye Lake', lat: 54.939846, lng: 68.944842, level:1.38},
  {name: 'Pogany Lake', lat: 54.921205, lng: 69.053476, level:1.37},
  {name: 'Wild Lake', lat: 54.840156, lng: 69.131957, level:1.35},
  {name: 'Kishtibish 1st Lake', lat: 54.970999, lng: 69.179717, level:1.34},
  {name: 'Kishtibish 2nd Lake', lat: 54.960140, lng: 69.162165, level:1.33},
  {name: 'Kishtibish 3rd Lake', lat: 54.954472, lng: 69.180190, level:31.3},
  {name: 'Penkovskoye Lake', lat: 54.962740, lng: 69.259045, level:2.3},
  {name: 'Solyonoye Lake', lat: 54.82674898549412, lng:69.12653062585713, level:0.55},
])
</script>
