<template>
  <section id="section-map">
    <div class="title">
      <p>clientes</p>
      <p>mapa</p>
    </div>
    <div class="maps">
    <div id="map"></div>
    <SubSectionMapInfo :card-info="cardInfo" @visit-establishment="centerMapOnEstablishment"/>
  </div>
  </section>
</template>


<script>
import SubSectionMapInfo from '../components/subsection_map_info.vue'
export default {
  name: "SectionMap",
  data() {
    return {
      map: null,
      cardInfo: [
      ],
    };
  },
  components:{
    SubSectionMapInfo,
  },
  mounted() {
    this.initMapbox();
  },
  methods: {
    async initMapbox() {
      const response = await fetch(
        'https://api.maptiler.com/maps/basic-v2/style.json?key=49RUadURGLXgj0A7AWfo'
      );
      try {
        if (!response.ok) throw Error(response.statusText);
        const style = await response.json();
        const map = new mapboxgl.Map({
          container: 'map',
          style: style,
          zoom: 7,
          center: [-48.845116, -26.303207],
        });
        this.map = map;
        this.initMap(map);
      } catch (error) {
        console.error({ error });
      }
    },
    initMap(map) {
      const bounds = new mapboxgl.LngLatBounds();
      const markers = [];

      function getComputedTranslateXY(obj) {
        const transArr = [];
        if (!window.getComputedStyle) return;
        const style = getComputedStyle(obj),
          transform = style.transform || style.webkitTransform || style.mozTransform;
        let mat = transform.match(/^matrix3d\((.+)\)$/);
        if (mat) return parseFloat(mat[1].split(', ')[13]);
        mat = transform.match(/^matrix\((.+)\)$/);
        mat ? transArr.push(parseFloat(mat[1].split(', ')[4])) : 0;
        mat ? transArr.push(parseFloat(mat[1].split(', ')[5])) : 0;
        return transArr;
      }

      function getWindowXYSize() {
        const windowXY = [];
        const w = window;
        const d = document;
        const e = d.documentElement;
        const g = d.getElementsByTagName('body')[0];
        const x = w.innerWidth || e.clientWidth || g.clientWidth;
        const y = w.innerHeight || e.clientHeight || g.clientHeight;
        windowXY.push(x, y);
        return windowXY;
      }

      const iconCity = `
    <path class="e-marker__icon e-marker__icon--city" d="M41.1,68.7V58.5L36,53.4l-5.1,5.1v3.4H20.8v23.7h30.5V68.7H41.1z M27.5,82.2h-3.4v-3.4h3.4V82.2z M27.5,75.4h-3.4
	V72h3.4V75.4z M27.5,68.7h-3.4v-3.4h3.4V68.7z M37.7,82.2h-3.4v-3.4h3.4V82.2z M37.7,75.4h-3.4V72h3.4V75.4z M37.7,68.7h-3.4v-3.4
	h3.4V68.7z M37.7,61.9h-3.4v-3.4h3.4V61.9z M47.9,82.2h-3.4v-3.4h3.4V82.2z M47.9,75.4h-3.4V72h3.4V75.4z"/>
`;

      const geojson = {
        "type": "FeatureCollection",
        "features": [
          {
            "type": "Feature",
            "properties": {
              "title": "Casa Ministro, Charutos & Whisky Lounge",
              "imageUrl": "src/assets/img/logo/casa_ministro_logo.png",
              "type": "Bar",
            },
            "geometry": {
              "type": "Point",
              "coordinates": [
              -48.846131066078904,
              -26.310174216183405,
              ]
            }
          },
          {
            "type": "Feature",
            "properties": {
              "title": "7 Grãos Pães e Doces",
              "imageUrl": "src/assets/img/logo/7_graos_logo.png",
              "type": "Padaria",
            },
            "geometry": {
              "type": "Point",
              "coordinates": [
              -48.920667672345175,
              -26.287165020260446,
              ]
            }
          },
          {
            "type": "Feature",
            "properties": {
              "title": "Neudorf Choperia",
              "imageUrl": "src/assets/img/logo/neudorf_logo.png",
              "type": "Hamburgueria",
            },
            "geometry": {
              "type": "Point",
              "coordinates": [
              -48.91875157359281,
              -26.287266018376062,
              ]
            }
          },
          {
            "type": "Feature",
            "properties": {
              "title": "Quinze Minutos",
              "imageUrl": "src/assets/img/logo/quinze_minutos_logo.png",
              "type": "Fornecedor de máquinas de café",
            },
            "geometry": {
              "type": "Point",
              "coordinates": [
              -48.872563761471085,
              -26.29339946894952,
              ]
            }
          },
          {
            "type": "Feature",
            "properties": {
              "title": "Sabores do Sul",
              "imageUrl": "src/assets/img/logo/sabores_do_sul_logo.png",
              "type": "Lanchonete",
            },
            "geometry": {
              "type": "Point",
              "coordinates": [
              -48.901370894604256,
              -26.292276301129796,
              ]
            }
          },
          {
            "type": "Feature",
            "properties": {
              "title": "Padilha AgroPet",
              "imageUrl": "src/assets/img/logo/agropet_padilha_logo.png",
              "type": "Pet Shop",
            },
            "geometry": {
              "type": "Point",
              "coordinates": [
              -48.90982112355096,
              -26.286743308298952,
              ]
            }
          }
        ]
      };

      function renderMarker(marker) {
    const { title, imageUrl, type } = marker.properties;
    const titleArr = title.split(' ');
    const titleLast = titleArr.slice(Math.ceil(titleArr.length / 2), titleArr.length);
    const titleFirst = titleArr.slice(0, Math.ceil(titleArr.length / 2));
    let currentIcon = '';
    
    switch(type) {
        case 'city':
            currentIcon = iconCity;
            break;
        default: 
            currentIcon = '';
    };
  
    return `
        <div>
            <svg class="e-marker" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 72 130.7" width="36">
                <defs>
                    <clipPath id="circle">
                        <path d="M36,97.4c15,0,27.3-12.2,27.3-27.3c0-15-12.2-27.3-27.3-27.3S8.7,55.1,8.7,70.2S21,97.4,36,97.4z"/>
                    </clipPath>
                </defs>
                <path class="e-marker__marker" d="M60.7,45.4C54.1,38.8,45.3,35.2,36,35.2c-9.3,0-18.1,3.6-24.7,10.3C4.6,52,1,60.8,1,70.2c0,6.3,1.5,11.6,4.6,16.7
      C8.4,91.3,12.1,95,16,98.9c7.3,7.2,15.5,15.4,19,30.5c0.1,0.5,0.5,0.8,1,0.8s0.9-0.3,1-0.8c3.5-15.1,11.7-23.3,19-30.5
      c3.9-3.9,7.6-7.6,10.4-12.1c3.1-5.1,4.6-10.3,4.6-16.7C71,60.8,67.4,52,60.7,45.4z M36,97.4c-15,0-27.3-12.2-27.3-27.3
      S21,42.9,36,42.9c15,0,27.3,12.2,27.3,27.3C63.3,85.2,51,97.4,36,97.4z"/>
          <path class="e-marker__circle" d="M36,97.4c15,0,27.3-12.2,27.3-27.3c0-15-12.2-27.3-27.3-27.3S8.7,55.1,8.7,70.2S21,97.4,36,97.4z"/>
                ${currentIcon}
                <image class="e-marker__image" width="100%" height="100%" clip-path="url(#circle)" xlink:href="${imageUrl}" />
              </svg>
        </div>
    `;
}

      function offSetMarker(marker, markerGrowSize, map) {
    // Set the max width and height of the marker and shrink it a bit by multiplying with 0.x. This is to compensate for padding around the marker
    const markerMaxWidth = (marker.offsetWidth * markerGrowSize) * 0.55;
    const markerMaxHeight = (marker.offsetHeight * markerGrowSize) * 0.7;
    const markerOffSetX = getComputedTranslateXY(marker)[0];
    const markerOffSetY = getComputedTranslateXY(marker)[1];
    if (
        markerOffSetY < markerMaxHeight
        || markerOffSetX < markerMaxWidth
        || (getWindowXYSize()[0] - markerOffSetX) < (markerMaxWidth + marker.offsetWidth)
    ) {
        let offSetY = 0;
        let offSetX = 0;

        if (markerOffSetY < markerMaxHeight) {            
            offSetY = markerOffSetY - markerMaxHeight;
        }

        if (markerOffSetX < markerMaxWidth) {
            offSetX = markerOffSetX - markerMaxWidth;
        }
        // Add `marker.offsetWidth` to this calculation because the position is calculated from top-left
        if((getWindowXYSize()[0] - markerOffSetX) < (markerMaxWidth + marker.offsetWidth)) {            
            offSetX = (markerMaxWidth + marker.offsetWidth) - (getWindowXYSize()[0] - markerOffSetX);
        }
        
        map.panBy([offSetX, offSetY]);
    }
}

      geojson.features.forEach((marker) => {
        const svgMarker = renderMarker(marker);
        // To get an actual DOM node instead of a string we append our marker to a dummy element and query it again with 'firstchild'. This way we retrieve a normal DOM node
        const placeholder = document.createElement('div');
        placeholder.innerHTML = svgMarker;
        const el = placeholder.firstChild;

        el.nextSibling.addEventListener('click', () => {
            map.flyTo({
                center: marker.geometry.coordinates,
                zoom: 11,
            });      
        });

        // Extend bounds with marker coordinates
        bounds.extend(marker.geometry.coordinates);

        markers.push(el.nextSibling);

        new mapboxgl.Marker(el.nextSibling, {offset: [0, -30]})
            .setLngLat(marker.geometry.coordinates)
            .addTo(map);
    });

      map.on('load', (e) => {
        setTimeout(() => {
          map.fitBounds(bounds, {
            padding: { top: 50, bottom: 50, left: 50, right: 50 },
            easing(t) {
              return t * (2 - t);
            },
          });
        }, 300);
      });

      markers.forEach((marker) => {
        const markerSVG = marker.querySelector('svg');
        const markerIcon = marker.querySelector('.e-marker__icon');
        const markerImage = marker.querySelector('.e-marker__image');
        const markerText = marker.querySelector('.e-marker__text');

        const markerRenderer = css(markerSVG, { enableHardwareAcceleration: false });
        const iconRenderer = svg(markerIcon);
        const imageRenderer = css(markerImage);
        const textRenderer = css(markerText);

        const markerGrowSize = 3;

        const markerScale = physics({
            from: 1,
            to: markerGrowSize,
            velocity: 20,
            spring: 300,
            friction: 0.8,
            onUpdate: (x) => markerRenderer.set('scale', x),
        });

        const iconScale = tween({
            from: 1,
            to: 0,
            duration: 300,
            ease: easing.backIn,
            onUpdate: (x) => iconRenderer.set('scale', x),
        });

        const imageScale = tween({
            from: 0,
            to: 1,
            duration: 300,
            ease: easing.backOut,
            onUpdate: (x) => imageRenderer.set('scale', x),
        });

        const textToggle = tween({
            from: 0,
            to: 1,
            duration: 300,
            ease: easing.backOut,
            onUpdate: (x) => textRenderer.set('opacity', x),
        });

        const hoverTimeline = timeline([
            iconScale,
            '0',
            imageScale,
            '-100',
            textToggle,
        ]);

        marker.addEventListener('mouseenter', () => {
            offSetMarker(marker, markerGrowSize, map);
            markerScale.props.from = 1;
            markerScale.props.to = markerGrowSize;
            imageScale.props.playDirection = 1;
            iconScale.props.playDirection = 1;
            hoverTimeline.props.playDirection = 1;
            textToggle.props.playDirection = 1; 
            markerScale.start();
            hoverTimeline.start();  
        });

        marker.addEventListener('mouseleave', () => {
            markerScale.props.from = markerGrowSize;
            markerScale.props.to = 1;
            hoverTimeline.reverse();
            hoverTimeline.start();
            markerScale.start();
        });

    });
    },
    centerMapOnEstablishment(establishment) {
      if (this.map) { // Verifique se a instância do mapa está disponível
        this.map.flyTo({
          center: establishment.localcoordenades,
          zoom: 16,
        });
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

.e-marker {
  transform-origin: bottom center;
  cursor: pointer;
}

.e-marker__marker {
  fill: #fff;
}

.e-marker__icon {
  fill: #fff;
}

.e-marker__image {
  transform: scale(0);
  transform-origin: 50% 50%;
}

.e-marker__circle {
  display: none;
}

.e-marker__text {
  font-size: 12px;
  font-family: brandon-grotesque, sans-serif;
  text-align: center;
  opacity: 0;
  color: #fff;
  fill: #fff;
  transform-origin: 50% 50%;
  text-anchor: middle;
}

#section-map {
  width: 90vw;
  height: 35vh;
  margin: 15px;
  display: flex;
  flex-direction: column
}

#map {
  flex: 1;
  height: 42vh;
  border-radius: 10px;
  box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.2);
  border: 5px solid transparent;
  background: linear-gradient(45deg, #d7a449, #fff);
}


#map-info {
  box-sizing: border-box;
}

.info-box {
  background-color: #fff;
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.title {
  display: flex;
  font-size: 24px; /* Aumenta o tamanho da fonte para 24 pixels */
  color: #d7a449; /* Altera a cor do texto para verde */
  text-shadow: 2px 2px 4px rgba(0,0,0,0.5); /* Adiciona uma sombra ao texto */
  justify-content: space-between
}

.maps{
  display: flex;
  flex-direction: row-reverse;
}

p{
  margin: 0px;
}
</style>
