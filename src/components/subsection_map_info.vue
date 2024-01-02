<template>
  <div id="map-info" class="scroll-container">
    <div
      v-for="(card, index) in cards"
      :key="index"
      class="card"
      :class="{ expanded: card.expanded }"
      @click="toggleCard(index)"
      :style="{ backgroundImage: cardInfo[index].backgroundImage }"
    >
      <div class="card-body">
        <h5 class="card-title">{{ cardInfo[index].title }}</h5>
        <p class="card-text">{{ cardInfo[index].text }}</p>
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
            title: "Casa Ministro",
            text: "Conteúdo do Card 1.",
            backgroundImage: "url('src/assets/portifolio/holofote.jpg')",
          },
          {
            title: " 7 Grãos",
            text: "Conteúdo do Card 2.",
            backgroundImage: "url('src/assets/portifolio/holofote.jpg')",
          },
          {
            title: "Neudorf Choperia",
            text: "Conteúdo do Card 3.",
            backgroundImage: "url('src/assets/portifolio/holofote.jpg')",
          }
        ],
      };
    },
    methods: {
      toggleCard(index) {
      this.cards.forEach((card, i) => {
        if (i === index) {
          this.$set(this.cards, i, { expanded: !card.expanded });
        } else {
          this.$set(this.cards, i, { expanded: false });
        }
      });
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

.card.expanded {
  width: 95%;
  height: 70%;
  border-radius: 20px;
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

.card.expanded {
  background-image: url('src/assets/portifolio/holofote.jpg');
}

::-webkit-scrollbar {
    width: 10px; /* Largura da barra de rolagem */
}

::-webkit-scrollbar-thumb {
    background-color: #d7a449; /* Cor da linha da barra de rolagem */
    border-radius: 6px; /* Borda arredondada da linha */
}
  </style>
  