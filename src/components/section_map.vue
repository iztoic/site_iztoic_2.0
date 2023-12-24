<template>
  <section id="section-map">
    <div id="map"></div>
  </section>
</template>

<script>
export default {
  name: "SectionMap",
  mounted() {
    this.initMapbox();
  },
  methods: {
    async initMapbox() {
      try {
        const response = await fetch(
          "https://api.maptiler.com/maps/hybrid/style.json?key=uB5DVeztu62syAixuO9B"
        );

        if (!response.ok) {
          throw Error(response.statusText);
        }

        const style = await response.json();
        const map = new mapboxgl.Map({
          container: "map",
          style: style,
          zoom: 10,
          center: [-48.845116, -26.303207],
        });

        // Dados dos marcadores
        const markersData = [
          { color: "#FF0000", coordinates: [-48.845116, -26.303207] },
          // Adicione mais marcadores conforme necessário
        ];

        // Adiciona os marcadores ao mapa
        markersData.forEach(markerData => {
          const marker = new mapboxgl.Marker({ color: markerData.color })
            .setLngLat(markerData.coordinates)
            .addTo(map);
        });

      } catch (error) {
        console.error({ error });
        const errorWrap = document.createElement("div");
        errorWrap.innerHTML =
          "<h1>Uh Oh, houve um erro ao carregar o mapa 😭</h1>";
        document.body.appendChild(errorWrap);
      }
    },
  },
};
</script>

<style scoped>
@import url('https://api.tiles.mapbox.com/mapbox-gl-js/v0.49.0/mapbox-gl.css');

* {
  box-sizing: border-box;
}

#map {
  top: 0;
  left: 0;
  width: 50vw;
  height: 60vh;
  border: 2px solid #ccc;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
</style>
