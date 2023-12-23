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
  border: 2px solid #ccc; /* Adiciona uma borda de 2 pixels sólida com cor cinza claro */
  border-radius: 10px; /* Adiciona bordas arredondadas para um visual mais moderno */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* Adiciona uma sombra suave ao redor do mapa */
}
</style>