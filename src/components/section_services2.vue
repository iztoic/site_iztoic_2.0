<template>
  <section class="game-section">
    <div class="row-list">
          <div class="services-title text-center">
            <h2 class="section-heading">Serviços</h2>
            <h3 class="section-subheading text-muted">Verifique as opções.</h3>
          </div>
        </div>
    <div class="owl-carousel custom-carousel owl-theme">
      <div v-for="(game, index) in games" :key="index" :class="{ 'item-card': true, 'active': index === activeIndex }" :style="{ 'background-image': 'url(' + game.image + ')' }" @click="toggleActive(index)">
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
        { name: "Copyright", description: "O copyright, muitas vezes conhecido como `copy`, é a arte de desenvolver textos persuasivos que cativam o publico e o levam a tomar a ação. É a linguagem que vende produtos, idéias e histórias.", image: "src/assets/img/VFX.png" },
        { name: "Video Maker", description: "O Video Maker é o Profissional da produção de videos, que contam histórias de forma vizual e envolvente. O video se tornou uma ferramenta de comunicação primordial, e sua produção envolve a criação de conteudo impactante, atraindo a atenção do publico.", image: "src/assets/img/Videography.png" },
        { name: "Social Media", description: "As redes sociais desempenham um papel criticona construção e manutenção do publico. Os profissionais de Social Media são especialistas em gerenciar a presença de uma marca em plataformas como Instagram e Facebook.", image: "src/assets/img/photography.png" },
        { name: "Marketing Digital", description: "O Marketing Digital é o guarda-chuva sob o qual todas essas disciplinas se reunem. Ele abrange estratégias e táticas para promover e comercializar produtos ou serviços online. Desde anuncios pagos e otimização de mecanismos de busca até o uso eficaz de redes sociais, o marketing digital envolve a criação de estratégias que maximizam a visibilidade e o alcance online.", image: "src/assets/img/Videography.png" },
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
@charset "utf-8";

/******* Fonts Import Start **********/
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");
/********* Fonts Face CSS End **********/

/******* Common Element CSS Start ******/

body {
  font-family: "Roboto", sans-serif;
  font-size: 16px;
}
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
  align-content: flex-end
}
/******* Common Element CSS End *********/


/******* Middle section CSS Start ******/
/* -------- Landing page ------- */
.game-section {
  padding: 60px 50px;
  padding-top: 0px;
}
.game-section .owl-stage {
  display: flex;
  flex-wrap: nowrap; /* Evita que os elementos quebrem para a próxima linha */
  margin: 0; /* Remove the margin */
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
  transition: all 0.4s ease-in-out;
  -webkit-transition: all 0.4s ease-in-out;
  cursor: pointer;
  margin-right: 5px; 
}
.game-section .item-card.active {
  width: calc(100% / 4 - 5px);
  box-shadow: 12px 40px 40px rgba(0, 0, 0, 0.25);
  -webkit-box-shadow: 12px 40px 40px rgba(0, 0, 0, 0.25);
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


.section-heading {
  color:#d7a449; /* Cor do título principal */
  text-shadow: 3px 3px 0 hsl(0, 0%, 0%, 0.25);
}

.section-subheading {
  color: #777; /* Cor do sub-título */
}

.services-title{
  display: flex;
  flex-direction: column;
}
.row-list {
  margin-bottom: 5px; /* Adiciona espaço entre as linhas (rows) */
}
/******** Middle section CSS End *******/

/***** responsive css Start ******/

@media (min-width: 992px) and (max-width: 1199px) {
  h2 {
    margin-bottom: 32px;
  }
  h3 {
    margin: 0 0 8px;
    font-size: 24px;
    line-height: 32px;
  }

  /* -------- Landing page ------- */
  .game-section {
    padding: 50px 30px;
  }
  .game-section .item {
    margin: 0 12px 60px;
    width: 260px;
    height: 360px;
  }
  .game-section .item.active {
    width: 400px;
  }
  .game-section .item-desc {
    transform: translateY(calc(100% - 46px));
    -webkit-transform: translateY(calc(100% - 46px));
  }
}

@media (min-width: 768px) and (max-width: 991px) {
  h2 {
    margin-bottom: 32px;
  }
  h3 {
    margin: 0 0 8px;
    font-size: 24px;
    line-height: 32px;
  }
  .line-title {
    width: 330px;
  }

  /* -------- Landing page ------- */
  .game-section {
    padding: 50px 30px 40px;
  }
  .game-section .item {
    margin: 0 12px 60px;
    width: 240px;
    height: 330px;
  }
  .game-section .item.active {
    width: 360px;
  }
  .game-section .item-desc {
    transform: translateY(calc(100% - 42px));
    -webkit-transform: translateY(calc(100% - 42px));
  }
}

@media (max-width: 767px) {
  body {
    font-size: 14px;
  }
  h2 {
    margin-bottom: 20px;
  }
  h3 {
    margin: 0 0 8px;
    font-size: 19px;
    line-height: 24px;
  }
  .line-title {
    width: 250px;
  }

  /* -------- Landing page ------- */
  .game-section {
    padding: 30px 15px 20px;
  }
  .game-section .item {
    margin: 0 10px 40px;
    width: 200px;
    height: 280px;
  }
  .game-section .item.active {
    width: 270px;
    box-shadow: 6px 10px 10px rgba(0, 0, 0, 0.25);
    -webkit-box-shadow: 6px 10px 10px rgba(0, 0, 0, 0.25);
  }
  .game-section .item-desc {
    padding: 0 14px 5px;
    transform: translateY(calc(100% - 42px));
    -webkit-transform: translateY(calc(100% - 42px));
  }
}


</style>
