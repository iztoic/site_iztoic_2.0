<template>
  <div>
    <section id="section-team" class="bg-light-gray">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 text-center">
            <h3 class="section-subheading">Conheça nossa equipe</h3>
          </div>
        </div>
        <div class="row">
          <div v-for="(member, index) in teamMembers" :key="index" class="info-card">
            <div class="team-member">
              <h4>{{ member.name }}</h4>
              <p class="text-muted">{{ member.occupation }}</p>
              <div :class="'card card' + index" :style="{ 'background-image': 'url(' + member.background + ')' }">
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
          background: "src/assets/img/perfil_desc.png",
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
          background: "src/assets/img/perfil_desc.png",
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
          background: "src/assets/img/perfil_dani.jpg",
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
          background: "src/assets/img/perfil_bina.jpg",
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

h3 { 
  font-size: var(--all_text_size_h3);
  color: var(--primary_gold_color);
  text-shadow: var(--all_page_text_shadow);
}
p { font-size: var(--all_text_size_p);}

h4 {
  color:var(--primary_gold_color);
  font-size: var(--all_text_size_h5);
  text-shadow: var(--all_page_text_shadow);
}

h2 {
  font-family: var(--all_text_font_family);
  color:var(--secundary_gray_color);
  margin: 20px;
  opacity: 0;
  transition: opacity 1s;
}

.row {
  justify-content: center;
}

</style>



<style scoped>
.container {
  width: var(--all_full_section_container_width);
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin: 0 auto;
  flex-direction: column;
}

.col-sm-4 {
  padding-top: 20px;
  padding-bottom: 20px;
}

.border:hover {
  border: 1px solid white;
}

.info-card{
  display: flex;
  justify-content: center;
  padding: 5px;
}

.card {
  height: 50vh;
  width: 40vh;
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

.border {
  height: 95%;
  width: 95%;
  background: transparent;
  border-radius: 10px;
  transition: border 1s;
  position: relative;
}

.card0, .card1, .card2, .card3, .card4 {
  background: var(--section_team_cards_background_before);
  background-size: var(--section_team_cards_background_size);
  filter: var(--section_team_cards_grayscale_filter);
}

.card0:hover,.card1:hover,.card2:hover,.card3:hover,.card4:hover {
  background: var(--section_team_cards_background_after);
  background-size: var(--section_team_cards_background_size_hoover);
  filter: var(--section_team_cards_grayscale_filter);
}

.card0:hover h2, .card0:hover .fa,
.card1:hover h2, .card1:hover .fa,
.card2:hover h2, .card2:hover .fa,
.card3:hover h2, .card3:hover .fa,
.card4:hover h2, .card4:hover .fa {
  opacity: 1;
}

.fa {
  opacity: 0;
  transition: opacity 1s;
}

.icons {
  position: absolute;
  fill: #fff;
  color: #fff;
  height: 130px;
  top: 166px;
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
  width: 250px;
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
  }
}

@media (max-width: 575px) {
  .col-md-6 {
    flex-basis: 100%;
    max-width: 100%;
    padding: 0 15px;
    margin-bottom: 30px;
  }

  .card {
    max-width: 300px;
  }

  .row{
    justify-items: flex-start;
  }
}
</style>
