<template>
    <div id="map-info" class="scroll-container">
      <div
        v-for="(card, index) in cards"
        :key="index"
        class="card"
        :class="{ expanded: card.expanded }"
        @click="toggleCard(index)"
      >
        <div class="card-body">
          <h5 class="card-title">Card {{ index + 1 }}</h5>
          <p class="card-text">Conteúdo do Card {{ index + 1 }}.</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "SubSectionMapInfo",
    data() {
      return {
        cards: Array(5).fill().map(() => ({ expanded: false })),
      };
    },
    methods: {
      toggleCard(index) {
        this.$set(this.cards, index, { expanded: !this.cards[index].expanded });
      },
    },
  };
  </script>
  
  <style scoped>
  #map-info {
    height: 70%;
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
    width: 100%;
    margin: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    transition: width 0.3s; /* Adicionado para animação suave */
  }
  
  .card.expanded {
    width: 100%;
  }
  
  .card-body {
    padding: 1rem;
    cursor: pointer;
  }
  
  .card-title {
    font-size: 1.5rem;
    margin-bottom: 10px;
  }
  
  .card-text {
    font-size: 1rem;
    overflow-y: auto;
    max-height: 100px; /* Defina a altura máxima desejada */
  }
  </style>
  