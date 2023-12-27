<template>
  <div>
    <section id="section-team" class="bg-light-gray">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 text-center">
            <h3 class="section-subheading text-muted">
              Conheça nossa equipe
            </h3>
          </div>
        </div>
        <div class="row">
          <div class="col-sm-4">
            <div class="team-member">
              <h4>Jonatan Keller</h4>
              <p class="text-muted">Developer</p>
              <div class="card card0">
                <div class="border">
                  <h2>Jonatan Keller</h2>
                  <div class="icons">
                    <i class="fa fa-linkedin" aria-hidden="true" onclick="window.open('https://www.linkedin.com/in/jonatankeller/', '_blank')"></i>
                    <i class="fa fa-instagram" aria-hidden="true" onclick="window.open('https://www.instagram.com/kellerjonatan/', '_blank')"></i>
                    <i class="fa fa-twitter" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-facebook" aria-hidden="true" onclick="window.open('')"></i>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-sm-4">
            <div class="team-member">
              <h4>Dionei Caliel</h4>
              <p class="text-muted">Ocupation</p>
              <div class="card card1">
                <div class="border">
                  <h2>Dionei Caliel</h2>
                  <div class="icons">
                    <i class="fa fa-linkedin" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-instagram" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-twitter" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-facebook" aria-hidden="true" onclick="window.open('')"></i>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-sm-4">
            <div class="team-member">
              <h4>Gabriel Oliveira</h4>
              <p class="text-muted">Ocupation</p>
              <div class="card card2">
                <div class="border">
                  <h2>Gabriel Oliveira</h2>
                  <div class="icons">
                    <i class="fa fa-linkedin" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-instagram" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-twitter" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-facebook" aria-hidden="true" onclick="window.open('')"></i>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-sm-4">
            <div class="team-member">
              <h4>Dani</h4>
              <p class="text-muted">Ocupation</p>
              <div class="card card3">
                <div class="border">
                  <h2>Dani</h2>
                  <div class="icons">
                    <i class="fa fa-linkedin" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-instagram" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-twitter" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-facebook" aria-hidden="true" onclick="window.open('')"></i>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-sm-4">
            <div class="team-member">
              <h4>Will</h4>
              <p class="text-muted">Ocupation</p>
              <div class="card card4">
                <div class="border">
                  <h2>Will</h2>
                  <div class="icons">
                    <i class="fa fa-linkedin" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-instagram" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-twitter" aria-hidden="true" onclick="window.open('')"></i>
                    <i class="fa fa-facebook" aria-hidden="true" onclick="window.open('')"></i>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
  
<script>
export default {
  name: "SectionTeam",
  components: {
  }
};
</script>
  
<style scoped>

section {
  padding-top: 10vh;
  border: 3px solid #d7a449;
  border-right: 3px solid transparent;
}

h4{
  color:#d7a449;
  text-shadow: 3px 3px 0 hsl(0, 0%, 0%, 0.25);
}

/* Container */
.cardcontainer {
  height: 100vh;
  width: 100vw;
  max-height: 800px;
  max-width: 1280px;
  min-height: 600px;
  min-width: 1000px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin: 0 auto;
}

.row {
  justify-content: center;
}

.col-sm-4 {
  padding-top: 20px;
  padding-bottom: 20px;
}

/* Border */
.border {
  height: 369px;
  width: 290px;
  background: transparent;
  border-radius: 10px;
  transition: border 1s;
  position: relative;
}

.border:hover {
  border: 1px solid white;
}

/* Card */
.card {
  height: 379px;
  width: 300px;
  background: grey;
  border-radius: 10px;
  transition: background 0.8s;
  overflow: hidden;
  background: black;
  box-shadow: 0 70px 63px -60px #000000;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

/* Card 0 */
.card0 {
  background: url('src/assets/portifolio/perfil_keller2.png') center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card0:hover {
  background: url('src/assets/portifolio/perfil_keller2.png') left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card0:hover h2,
.card0:hover .fa {
  opacity: 1;
}

/* Card 1 */
.card1 {
  background: url("src/assets/portifolio/perfil_desc.png") center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card1:hover {
  background: url("src/assets/portifolio/perfil_desc.png") left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card1:hover h2,
.card1:hover .fa {
  opacity: 1;
}

/* Card 2 */
.card2 {
  background: url("src/assets/portifolio/perfil_desc.png") center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card2:hover {
  background: url("src/assets/portifolio/perfil_desc.png") left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card2:hover h2,
.card2:hover .fa {
  opacity: 1;
}

/* Card 3 */
.card3 {
  background: url("src/assets/portifolio/perfil_desc.png") center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card3:hover {
  background: url("src/assets/portifolio/perfil_desc.png") left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card3:hover h2,
.card3:hover .fa {
  opacity: 1;
}

/* Card 4 */
.card4 {
  background: url("src/assets/portifolio/perfil_desc.png") center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card4:hover {
  background: url("src/assets/portifolio/perfil_desc.png") left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card4:hover h2,
.card4:hover .fa {
  opacity: 1;
}


/* Heading 2 */
h2 {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  color:#837878;
  margin: 20px;
  opacity: 0;
  transition: opacity 1s;
}

/* Font Awesome */
.fa {
  opacity: 0;
  transition: opacity 1s;
}

/* Icons */
.icons {
  position: absolute;
  fill: #fff;
  color: #fff;
  height: 130px;
  top: 226px;
  width: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  text-align: center;
  padding-top: 2px;
  padding-bottom: 15px;
}

.icons i {
  text-decoration: none;
  font-size: 17px;
  color: #ffffff;
  padding: 0 10px;
  transition-duration: 0.4s;
  transition-property: all;
}

.icons i:hover {
  color:#583f13;
  transform: scale(1.5);
}
</style>
  