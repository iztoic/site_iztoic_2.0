<template>
  <section class="game-section">
          <div class="page-top">
            <h2 class="page-title">Serviços</h2>
            <h3 class="page-description">Verifique as opções.</h3>
          </div>
    <div class="owl-carousel custom-carousel owl-theme">
      <div v-for="(game, index) in games" :key="index" :class="{ 'item-card': true, 'active': index === activeIndex }" :style="{ 'background-image': 'url(' + game.image + ')' } " @click="toggleActive(index)">
        <div class="item-card-desc">
          <h3>{{ game.name }}</h3>
          <p>{{ game.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SectionService",
  data() {
    return {
      activeIndex: null,
      games: [
        { name: "Copyright", description: "O copyright, muitas vezes conhecido como `copy`, é a arte de desenvolver textos persuasivos que cativam o publico e o levam a tomar a ação. É a linguagem que vende produtos, idéias e histórias.", image: "src/assets/img/copywright.png" },
        { name: "Video Maker", description: "O Video Maker é o Profissional da produção de videos, que contam histórias de forma vizual e envolvente. O video se tornou uma ferramenta de comunicação primordial, e sua produção envolve a criação de conteudo impactante, atraindo a atenção do publico.", image: "src/assets/img/videomaker.png" },
        { name: "Social Media", description: "As redes sociais desempenham um papel criticona construção e manutenção do publico. Os profissionais de Social Media são especialistas em gerenciar a presença de uma marca em plataformas como Instagram e Facebook.", image: "src/assets/img/equipment.png" },
        { name: "Marketing Digital", description: "O Marketing Digital é o guarda-chuva sob o qual todas essas disciplinas se reunem. Ele abrange estratégias e táticas para promover e comercializar produtos ou serviços online. Desde anuncios pagos e otimização de mecanismos de busca até o uso eficaz de redes sociais, o marketing digital envolve a criação de estratégias que maximizam a visibilidade e o alcance online.", image: "src/assets/img/perfil01.png" },
      ]
    };
  },
  mounted() {
    $(".custom-carousel").owlCarousel({
      autoWidth: true,
      loop: true
    });
  },
  methods: {
    toggleActive(index) {
      this.activeIndex = this.activeIndex === index ? null : index;
    }
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

.clear {
  clear: both;
}
img {
  max-width: 100%;
  border: 0px;
}
ul,
ol {
  list-style: none;
}
a {
  text-decoration: none;
  color: inherit;
  outline: none;
  transition: all 0.4s ease-in-out;
  -webkit-transition: all 0.4s ease-in-out;
}
a:focus,
a:active,
a:visited,
a:hover {
  text-decoration: none;
  outline: none;
}
a:hover {
  color: #e73700;
}

button {
  outline: none !important;
}
div{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.game-section .item-card {
  margin: 0 5px 30px;
  width: calc(75% / 4 - 5px);
  height: 400px;
  display: flex;
  display: -webkit-flex;
  align-items: flex-end;
  -webkit-align-items: flex-end;
  background: #343434 no-repeat center center / cover;
  border-radius: 16px;
  overflow: hidden;
  position: relative;
  transition: all 0.3s ease;
  -webkit-transition: all 0.4s ease-in-out;
  cursor: pointer;
  margin-right: 5px; 
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  
  
}
.game-section .item-card.active {
  width: calc(100% / 4 - 5px);
  box-shadow: 12px 40px 40px rgba(0, 0, 0, 0.25);
  -webkit-box-shadow: 12px 40px 40px rgba(0, 0, 0, 0.25);
  background-color: #f9f9f9; /* Cor de fundo mais clara */
}
.game-section .item-card:after {
  content: "";
  display: block;
  position: absolute;
  height: 100%;
  width: 100%;
  left: 0;
  top: 0;
  background-image: linear-gradient(rgba(0, 0, 0, 0), rgba(0, 0, 0, 1));
}
.game-section .item-card-desc {
  padding: 0 24px 12px;
  color: #fff;
  position: relative;
  z-index: 1;
  overflow: hidden;
  background-color: rgba(41, 41, 41, 0.5); 
  transform: translateY(calc(100% - 54px));
  -webkit-transform: translateY(calc(100% - 54px));
  transition: all 0.4s ease-in-out;
  -webkit-transition: all 0.4s ease-in-out;
}
.game-section .item-card.active .item-card-desc {
  transform: none;
  -webkit-transform: none;
}
.game-section .item-card-desc p {
  opacity: 0;
  -webkit-transform: translateY(32px);
  transform: translateY(32px);
  transition: all 0.4s ease-in-out 0.2s;
  -webkit-transition: all 0.4s ease-in-out 0.2s;
}
.game-section .item-card.active .item-card-desc p {
  opacity: 1;
  -webkit-transform: translateY(0);
  transform: translateY(0);
}
.game-section .owl-theme.custom-carousel .owl-dots {
  margin-top: -20px;
  position: relative;
  z-index: 5;
}

/* Ajusta cores e fontes */
.game-section .item-card-desc h3 {
  color: #d7a449; /* Cor do título */
  font-size: 22px; /* Tamanho da fonte do título */
  text-wrap: nowrap;
}

.game-section .item-card-desc p {
  text-align: justify;
  color: #bebcbc; /* Cor do texto */
  font-size: 14px; /* Tamanho da fonte do texto */
}



/* -------- Landing page ------- */
.game-section {
  padding-top: 0px;
}

.game-section .item-card {
  margin: 0 5px 30px;
  width: calc(90% / 3 - 5px);
  height: 400px;
  display: flex;
  align-items: flex-end;
  background: #343434 no-repeat center center / cover;
  border-radius: 16px;
  overflow: hidden;
  position: relative;
  transition: all 0.3s ease;
  cursor: pointer;
  margin-right: 5px; 
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.game-section .item-card.active {
  width: calc(100% / 4 - 5px);
  box-shadow: 12px 40px 40px rgba(0, 0, 0, 0.25);
  background-color: #f9f9f9; /* Cor de fundo mais clara */
}

.game-section .item-card:after {
  content: "";
  display: block;
  position: absolute;
  height: 100%;
  width: 100%;
  left: 0;
  top: 0;
  background-image: linear-gradient(rgba(0, 0, 0, 0), rgba(0, 0, 0, 1));
}

.game-section .item-card-desc {
  padding: 0 24px 12px;
  color: #fff;
  position: relative;
  z-index: 1;
  overflow: hidden;
  background-color: rgba(41, 41, 41, 0.5); 
  transform: translateY(calc(100% - 54px));
  transition: all 0.4s ease-in-out;
}

.game-section .item-card.active .item-card-desc {
  transform: none;
}

.game-section .item-card-desc p {
  opacity: 0;
  transform: translateY(32px);
  transition: all 0.4s ease-in-out 0.2s;
}

.game-section .item-card.active .item-card-desc p {
  opacity: 1;
  transform: translateY(0);
}

.game-section .owl-theme.custom-carousel .owl-dots {
  margin-top: -20px;
  position: relative;
  z-index: 5;
}

/* Ajusta cores e fontes */
.game-section .item-card-desc h3 {
  color: #d7a449; /* Cor do título */
  font-size: 22px; /* Tamanho da fonte do título */
}

.game-section .item-card-desc p {
  text-align: justify;
  color: #bebcbc; /* Cor do texto */
  font-size: 14px; /* Tamanho da fonte do texto */
}

@media screen and (max-width: 767px) {
  .game-section .item-card {
    width: calc(75% / 1 - 5px); /* Manter o tamanho original dos cards */
    margin-right: 5px; /* Adicionar margem direita para separar os cards */
  }

  .game-section .item-card.active {
    width: calc(100% - 5px); /* Ajustar a largura do card ativo */
  }
  
  .game-section .item-card-desc {
    padding: 0 24px 12px;
  }

  .game-section .item-card.active .item-card-desc {
    transform: none; /* Manter o texto visível */
  }

  .game-section .item-card-desc p {
    opacity: 1; /* Manter o texto visível */
    transform: translateY(0); /* Manter o texto visível */
  }
}

</style>
