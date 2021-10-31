<template>
  <div class="flex flex-col h-screen max-h-screen">
    <div
      class="
        z-20
        flex
        justify-center
        relative
        px-4
        pt-8
        pb-32
        bg-gray-900
        text-white
      "
    >
      <div class="w-full max-w-screen-sm">
        <h1 class="text-white text-center text-3xl pb-4">IP Address Tracker</h1>
        <div class="flex relative">
          <span class="absolute top-2 left-2">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              viewBox="0 0 20 20"
              fill="gray"
            >
              <path
                fill-rule="evenodd"
                d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
                clip-rule="evenodd"
              />
            </svg>
          </span>
          <input
            type="text"
            class="
              flex-1
              py-2
              px-6
              text-center
              rounded-md
              focus:outline-none
              text-gray-600
              font-medium
              shadow-lg
            "
            placeholder="IP Address"
          />
        </div>
      </div>
      <!-- show ip information -->
      <Info />
    </div>
    <!-- Map -->
    <div id="map" class="h-full z-10"></div>
  </div>
</template>

<script>
import Info from '@/components/Info.vue'
import leaflet from 'leaflet'
import { onMounted, ref } from '@vue/runtime-core'
export default {
  name: 'Home',
  components: {
    Info,
  },
  setup() {
    const map = ref()
    let token = process.env.VUE_APP_TOKEN
    onMounted(() => {
      map.value = leaflet.map('map').setView([51.505, -0.09], 13)
      leaflet
        .tileLayer(
          `https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token=${token}`,
          {
            attribution:
              'Map data &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
            maxZoom: 18,
            id: 'mapbox/streets-v11',
            tileSize: 512,
            zoomOffset: -1,
            accessToken: `${token}`,
          }
        )
        .addTo(map.value)
    })
  },
}
</script>

<style></style>
