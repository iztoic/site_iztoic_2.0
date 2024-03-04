<template>
  <div>
    <section id="section-team" class="bg-light-gray">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 text-center">
            <h3 class="section-subheading text-muted">Conheça nossa equipe</h3>
          </div>
        </div>
        <div class="row">
          <div v-for="(member, index) in teamMembers" :key="index" class="info-card">
            <div class="team-member">
              <h4>{{ member.name }}</h4>
              <p class="text-muted">{{ member.occupation }}</p>
              <div :class="'card card' + index">
                <div class="border">
                  <h2>{{ member.name }}</h2>
                  <div class="icons">
                    <a v-for="(link, icon) in member.socialLinks" :key="icon" :href="link" target="_blank">
                      <i :class="'fa fa-' + icon" aria-hidden="true"></i>
                    </a>
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
  data() {
    return {
      teamMembers: [
        {
          name: "Jonatan Keller",
          occupation: "Developer",
          background: "src/assets/img/perfil_keller2.png",
          socialLinks: {
            linkedin: "https://www.linkedin.com/in/jonatankeller/",
            instagram: "https://www.instagram.com/kellerjonatan/",
            twitter: "",
            facebook: "",
          },
        },
        {
          name: "Dionei Caliel",
          occupation: "Ocupation",
          socialLinks: {
            linkedin: "",
            instagram: "",
            twitter: "",
            facebook: "",
          },
        },
        {
          name: "Gabriel Oliveira",
          occupation: "Ocupation",
          socialLinks: {
            linkedin: "",
            instagram: "",
            twitter: "",
            facebook: "",
          },
        },
        {
          name: "Dani",
          occupation: "Ocupation",
          socialLinks: {
            linkedin: "",
            instagram: "",
            twitter: "",
            facebook: "",
          },
        },
        {
          name: "Bina",
          occupation: "Ocupation",
          socialLinks: {
            linkedin: "",
            instagram: "",
            twitter: "",
            facebook: "",
          },
        },
        // Add more team members as needed
      ],
    };
  },
  methods: {
    openLink(link) {
      if (link) {
        window.open(link, "_blank");
      }
    },
  },
};
</script>

<style scoped>
@import url('../src/styles.css');
section {
  padding: var(--all_section_components_padding);
  border: var(--all_section_components_border);
  border-right: var(--all_section_components_border_right_transparent);
}

h3 { font-size: var(--all_text_size_h3);}
p { font-size: var(--all_text_size_p);}

h4{
  color:var(--primary_gold_color);
  font-size: var(--all_text_size_h4);
  text-shadow: var(--all_page_text_shadow);
}

/* Container */
.container {
  width: var(--all_full_section_container_width);
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin: 0 auto;
  flex-direction: column;
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

.team-member {
  width: 300px;
}

.info-card{
  display: flex;
  justify-content: center;
  padding: 5px;
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
  background: url('src/assets/img/perfil_keller2.png') center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card0:hover {
  background: url('src/assets/img/perfil_keller2.png') left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card0:hover h2,
.card0:hover .fa {
  opacity: 1;
}

/* Card 1 */
.card1 {
  background: url("src/assets/img/perfil_desc.png") center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card1:hover {
  background: url("src/assets/img/perfil_desc.png") left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card1:hover h2,
.card1:hover .fa {
  opacity: 1;
}

/* Card 2 */
.card2 {
  background: url("src/assets/img/perfil_desc.png") center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card2:hover {
  background: url("src/assets/img/perfil_desc.png") left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card2:hover h2,
.card2:hover .fa {
  opacity: 1;
}

/* Card 3 */
.card3 {
  background: url("src/assets/img/perfil_dani.jpg") center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card3:hover {
  background: url("src/assets/img/perfil_dani.jpg") left center no-repeat;
  background-size: 600px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card3:hover h2,
.card3:hover .fa {
  opacity: 1;
}

/* Card 4 */
.card4 {
  background: url("src/assets/img/perfil_bina.jpg") center center no-repeat;
  background-size: 300px;
  filter: grayscale(90%) contrast(1.7) brightness(0.7); /* Ajuste a intensidade da escala de cinza e o contraste conforme necessário */
  }

.card4:hover {
  background: url("src/assets/img/perfil_bina.jpg") left center no-repeat;
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

.team-member{
  padding-bottom: 10%;
}

@media (max-width: 768px) {
  .col-md-6 {
    flex-basis: 100%;
    max-width: 100%;
    padding: 0 15px;
    margin-bottom: 30px;
  }

  .card {
    max-width: 300px;
    margin: 0 auto;
  }
}
</style>
