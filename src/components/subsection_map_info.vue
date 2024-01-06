<template>
  <div id="map-info" class="scroll-container">
    <div
      v-for="(card, index) in cards"
      :key="index"
      class="card"
      @click="toggleCard(index)"
      :style="{ backgroundImage: cardInfo[index].backgroundImage }"
    >
    <div class="card-body">
        <h5 class="card-title">{{ cardInfo[index].name }}</h5>
        <p class="extra-text">{{ cardInfo[index].extraText }}</p>
        <p class="card-text">{{ cardInfo[index].address }}</p>
        <img :src="cardInfo[index].logo" alt="Logo" class="logo-img" />
        <button class="map-btn" @click="visitEstablishment(cardInfo[index])">Visite</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SubSectionMapInfo",
  data() {
    return {
      cards: Array(3).fill().map(() => ({ expanded: false })),
      cardInfo: [
        {
          name: "Casa Ministro",
          address: "R. Dr. Plácido Gomes, 320 - Anita Garibaldi, Joinville - SC, 89202-050",
          extraText: "Informações extras para o Casa Ministro.",
          logo: "src/assets/portifolio/casa_ministro_logo.png",
          backgroundImage: "url('src/assets/portifolio/holofote.jpg')",
          localcoordenades: [-48.846131066078904, -26.310174216183405],
        },
        {
          name: "7 Grãos",
          address: "R. Quinze de Novembro, 8862 - Vila Nova, Joinville - SC, 89237-680",
          extraText: "Informações extras para o 7 Grãos.",
          logo: "src/assets/portifolio/7_graos_logo.png",
          backgroundImage: "url('src/assets/portifolio/cigarette_box.jpg')",
          localcoordenades: [-48.920667672345175, -26.287165020260446],
        },
        {
          name: "Neudorf Choperia",
          address: "R. Quinze de Novembro, 8691 - Vila Nova, Joinville - SC, 89237-002",
          extraText: "Informações extras para o Neudorf Choperia.",
          logo: "src/assets/portifolio/neudorf_logo.png",
          backgroundImage: "url('src/assets/portifolio/holofote.jpg')",
          localcoordenades: [-48.91875157359281, -26.287266018376062],
        }
      ],
    };
  },
  methods: {
    visitEstablishment(establishment) {
      this.$emit('visit-establishment', establishment);
    },
  },
};
</script>
  
  <style scoped>
#map-info {
  height: 45vh;
  width: 40vw;
  margin-right: 2%;
  display: flex;
  overflow-y: scroll;
  flex-direction: column;
  align-items: center;
}

.scroll-container {
  display: flex;
  flex-shrink: 0;
}

.card {
  flex: 0 0 auto;
  width: 95%;
  margin: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: width 1.8s ease, height 1.8s ease, opacity 1.8s ease, border-radius 1.8s ease;
  background-size: cover;
  background-position: center;
  border-radius: 10px;
}


.card-body {
  padding: 1rem;
  cursor: pointer;
  color: #d7a449;
}

.card-title {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

.card-text {
  font-size: 1rem;
  max-height: 100px;
  overflow: hidden;
}

::-webkit-scrollbar {
    width: 10px; /* Largura da barra de rolagem */
}

::-webkit-scrollbar-thumb {
    background-color: #d7a449; /* Cor da linha da barra de rolagem */
    border-radius: 6px; /* Borda arredondada da linha */
}

.logo-img {
  max-width: 70px; /* Ajuste a largura máxima do logo conforme necessário */
  position: absolute;
  top: 5px;
  right: 20px;
  border: 2px solid #d7a449; /* Adicione uma borda ao redor do logo */
  border-radius: 50%; /* Faça a borda ser redonda */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3); /* Adicione uma sombra sutil ao redor do logo */
}

.map-btn {
  background-color: #d7a449;
  color: white;
  padding: 8px 16px;
  border: none;
  border-radius: 50% 50% 0 0; /* Faça o botão ter bordas arredondadas apenas na parte superior */
  cursor: pointer;
  margin-top: 10px;
  position: absolute;
  bottom: 17px;
  right: 56px;
  transform: translate(50%, 50%); /* Centralize o botão no canto inferior direito */
}
  </style>
  