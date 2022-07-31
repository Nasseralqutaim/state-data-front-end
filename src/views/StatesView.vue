<script>
/* global mapboxgl, mapboxgl*/

export default {
  data: function () {
    return {};
  },
  mounted: function () {
    mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_KEY;
    const map = new mapboxgl.Map({
      container: "map",
      style: "mapbox://styles/mapbox/streets-v11",
      center: [-96, 37.8],
      zoom: 3,
    });
    // map.on("mousemove", (e) => {
    //   const features = map.queryRenderedFeatures(e.point);

    //   // Limit the number of properties we're displaying for
    //   // legibility and performance
    //   const displayProperties = ["type", "properties", "id", "layer", "source", "sourceLayer", "state"];

    //   const displayFeatures = features.map((feat) => {
    //     const displayFeat = {};
    //     displayProperties.forEach((prop) => {
    //       displayFeat[prop] = feat[prop];
    //     });
    //     return displayFeat;
    //   });

    //   // Write object as string with an indent of two spaces.
    //   document.getElementById("features").innerHTML = JSON.stringify(displayFeatures, null, 2);
    // });

    console.log(map);
  },
  methods: {},
};
</script>

<!--  -->

<template>
  <div class="about">
    <h1>Find each state with their accompanying data:</h1>
    <div id="map"></div>
  </div>
</template>

<style>
#features {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  width: 50%;
  overflow: auto;
  background: rgba(255, 255, 255, 0.8);
}
#map canvas {
  cursor: crosshair;
}
#map {
  height: 300px;
}
</style>

<!-- pk.eyJ1IjoiZHF1dCIsImEiOiJjbDVhMjFtbTAwN3c5M2xvN3hkMTV5cmNtIn0.LN65tHleknenlufqUSb9bw -->
