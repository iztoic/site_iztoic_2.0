<template>
  <section id="section-testimonials">
    <figure class="snip1386">
      <img src="src/assets/portifolio/casa_ministro.png" class="background" />
      <figcaption>
        <blockquote>A IZTOIC superou minhas expectativas! Criatividade, eficiência e resultados impressionantes.</blockquote>
        <h5>- Casa Ministro</h5>
      </figcaption><img src="src/assets/portifolio/casa_ministro_logo.png" class="profile" />
    </figure>
    <figure class="snip1386 hover"><img src="src/assets/portifolio/7_graos.png" class="background" />
      <figcaption>
        <blockquote>Os serviços da IZTOIC são incríveis! Transformaram o meu negócio.</blockquote>
        <h5>- 7 Grãos</h5>
      </figcaption><img src="src/assets/portifolio/7_graos_logo.png" class="profile" />
    </figure>
    <figure class="snip1386"><img src="src/assets/portifolio/neudorf.png" class="background" />
      <figcaption>
        <blockquote>A IZTOIC entregou soluções tecnológicas excepcionais.</blockquote>
        <h5>- Neudorf Choperia</h5>
      </figcaption><img src="src/assets/portifolio/neudorf_logo.png" class="profile" />
    </figure>
  </section>
</template>

<script>
export default {
  name: "SectionTestimonials"
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
  max-width: 315px;
  max-height: 220px;
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
}</style>
