<template>
  <section id="section-testimonials">
    <figure v-for="(testimonial, index) in displayedTestimonials" :key="index" :class="'snip1386 ' + (index === activeIndex ? 'hover' : '')">
      <img :src="testimonial.backgroundImage" class="background" />
      <figcaption>
        <blockquote>{{ testimonial.quote }}</blockquote>
        <h5>{{ testimonial.clientName }}</h5>
      </figcaption>
      <img :src="testimonial.logo" class="profile" />
    </figure>

    <button @click="loadMore" v-if="showLoadMoreButton" class="ver-mais-btn">Ver mais</button>
  </section>
</template>

<script>
export default {
  name: "SectionTestimonials",
  data() {
    return {
      activeIndex: null,
      slideDirection: "right-to-left",
      testimonials: [
        {
          backgroundImage: "src/assets/img/clientes/casa_ministro.png",
          quote: "A IZTOIC superou minhas expectativas! Criatividade, eficiência e resultados impressionantes.",
          clientName: "- Casa Ministro",
          logo: "src/assets/img/logo/casa_ministro_logo.png",
        },
        {
          backgroundImage: "src/assets/img/clientes/7_graos.png",
          quote: "Os serviços da IZTOIC são incríveis! Transformaram o meu negócio.",
          clientName: "- 7 Grãos",
          logo: "src/assets/img/logo/7_graos_logo.png",
        },
        {
          backgroundImage: "src/assets/img/clientes/neudorf.png",
          quote: "A IZTOIC entregou soluções tecnológicas excepcionais.",
          clientName: "- Neudorf Choperia",
          logo: "src/assets/img/logo/neudorf_logo.png",
        },
        {
          backgroundImage: "src/assets/img/clientes/quinze_minutos.png",
          quote: "A IZTOIC entregou soluções tecnológicas excepcionais.",
          clientName: "- Quinze Minutos",
          logo: "src/assets/img/logo/quinze_minutos_logo.png",
        },
        {
          backgroundImage: "src/assets/img/clientes/sabores_do_sul.png",
          quote: "A IZTOIC entregou soluções tecnológicas excepcionais.",
          clientName: "- Sabores do Sul",
          logo: "src/assets/img/logo/sabores_do_sul_logo.png",
        },
        {
          backgroundImage: "src/assets/img/clientes/agropet_padilha.png",
          quote: "A IZTOIC entregou soluções tecnológicas excepcionais.",
          clientName: "- Agropet Padilha",
          logo: "src/assets/img/logo/agropet_padilha_logo.png",
        },
      ],
      displayedTestimonials: [],
      itemsToShow: 2,
      showLoadMoreButton: true,
    };
  },
  mounted() {
    this.loadTestimonials();
  },
  methods: {
    loadTestimonials() {
      // Randomly shuffle the testimonials array
      const shuffledTestimonials = this.testimonials.sort(() => Math.random() - 0.5);

      // Take the first 'itemsToShow' testimonials for display
      this.displayedTestimonials = shuffledTestimonials.slice(0, this.itemsToShow);

      // Check if there are more testimonials to show
      this.showLoadMoreButton = shuffledTestimonials.length > this.itemsToShow;
    },
    async loadMore() {
    // Adicione um pequeno delay antes de trocar os cards
    await new Promise(resolve => setTimeout(resolve, 300)); // Tempo em milissegundos

    // Remova depoimentos já exibidos
    const remainingTestimonials = this.testimonials.filter(testimonial => !this.displayedTestimonials.includes(testimonial));

    // Verifique se há depoimentos restantes suficientes para manter dois cards
    if (remainingTestimonials.length >= this.itemsToShow) {
      // Embaralhe os depoimentos restantes
      const shuffledTestimonials = remainingTestimonials.sort(() => Math.random() - 0.5);

      // Define a direção do carrossel
      this.slideDirection = "right-to-left";

      // Adicione dois novos depoimentos à lista existente
      this.displayedTestimonials = shuffledTestimonials.slice(0, this.itemsToShow);

      // Aguarde o término da transição e, em seguida, redefina a direção do carrossel
      setTimeout(() => {
        this.slideDirection = "";
      }, 600); // Ajuste conforme necessário

      // Atualize a flag de botão de carga
      this.showLoadMoreButton = remainingTestimonials.length > this.itemsToShow;
    } else {
      // Se não houver depoimentos suficientes, mantenha os já exibidos
      this.showLoadMoreButton = false;
    }
  },
  },
};
</script>


<style scoped>
@import url(https://fonts.googleapis.com/css?family=Playfair+Display:400,900);

section {
  padding-top: 50px;
  width: 100%;
  display: flex;
  justify-content: space-evenly;
}

blockquote {
  padding: 0;
  border-left: 0px;

}

.snip1386 {
  font-family: 'Playfair Display', Arial, sans-serif;
  position: relative;
  overflow: hidden;
  margin: 10px;
  min-width: 230px;
  max-width: 445px;
  max-height: 190px;
  width: 100%;
  color: #000000;
  text-align: left;
  font-size: 16px;
  border-radius: 10px;
  background-color: #000000;
}

.snip1386 * {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

.snip1386 .background {
  max-width: 100%;
  backface-visibility: hidden;
  opacity: 0.5;
}

.snip1386 figcaption {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  z-index: 1;
  opacity: 1;
  padding: 30px 10px 30px 0;
  background-color: #ffffff;
  width: 40%;
}

.snip1386 figcaption:before {
  position: absolute;
  top: 50%;
  -webkit-transform: translateY(-50%);
  transform: translateY(-50%);
  left: 100%;
  content: '';
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 120px 0 120px 120px;
  border-color: transparent transparent transparent #ffffff;
  margin-left: -1px;
}

.snip1386:after {
  position: absolute;
  bottom: 50%;
  left: 40%;
  content: '';
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 120px 120px 0 120px;
  border-color: rgba(255, 255, 255, 0.5) transparent transparent transparent;
}

.snip1386 h5,
.snip1386 blockquote {
  -webkit-transform: translateX(30px);
  transform: translateX(30px);
  margin: 0;
}

.snip1386 h5 {
  margin: 10px 0;
  line-height: 1.1em;
  font-weight: 900;
  color: #d7a449;
}

.snip1386 blockquote {
  font-size: 0.9em;
  font-style: italic;
}

.snip1386 .profile {
  position: absolute;
  width: 100px;
  border-radius: 50%;
  top: 50%;
  right: 25%;
  z-index: 1;
  -webkit-transform: translate(50%, -50%);
  transform: translate(50%, -50%);
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
  border: 2px solid #d7a449;
}

.credibility {
  align-items: center;
  display: flex;
}

.snip1386:hover {
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.6);
  transform: scale(1.1);
  transition: box-shadow 0.6s ease, transform 0.6s ease;
}

.snip1386:hover figcaption {
  transition: padding 0.6s ease;
}

.snip1386 .background {
  transition: opacity 0.3s ease;
}

.snip1386:hover .background {
  opacity: 1;
}

.snip1386 .profile {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.snip1386:hover .profile {
  transform: translate(50%, -50%) scale(1.1);
  box-shadow: 0 0 30px rgba(0, 0, 0, 0.5);
}
.ver-mais-btn {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #36424b;
    color: #fff;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s ease;
    border: 2px solid #d7a449; /* Adicione uma borda ao redor do logo */
  }

  .ver-mais-btn:hover {
    background-color: #1a2125;
    border: 2px solid #d7a449; /* Adicione uma borda ao redor do logo */

  }

  .right-to-left-enter-active,
.right-to-left-leave-active {
  transition: transform 0.6s ease;
}

.right-to-left-enter, .right-to-left-leave-to /* .right-to-left-leave-active in <2.1.8 */ {
  transform: translateX(100%);
}
  </style>
