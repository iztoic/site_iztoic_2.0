<template>
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
</template>

<script>
export default {
  name: 'SubSectionInfoCards',
  data() {
    return {
      teamMembers: [
        {
          name: "Jonatan Keller",
          occupation: "Desenvolvedor",
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
          occupation: "Marketing",
          background: "src/assets/img/perfil_caliel.png",
          socialLinks: {
            linkedin: "https://www.linkedin.com/in/caliel-oliveira-664113296",
            instagram: "https://www.instagram.com/dcaliel/",
            twitter: "",
            facebook: "",
          },
        },
        {
          name: "Gabriel",
          occupation: "Ocupation",
          background: "src/assets/img/perfil_desc.png",
          socialLinks: {
            linkedin: "",
            instagram: "https://www.instagram.com/gabrielrosaa__/",
            twitter: "",
            facebook: "",
          },
        },
        {
          name: "Dani",
          occupation: "Recursos Humanos",
          background: "src/assets/img/perfil_dani.jpg",
          socialLinks: {
            linkedin: "",
            instagram: "https://www.instagram.com/dani_martinsss/",
            twitter: "",
            facebook: "",
          },
        },
        {
          name: "Bina",
          occupation: "Social Media",
          background: "src/assets/img/perfil_bina.jpg",
          socialLinks: {
            linkedin: "",
            instagram: "https://www.instagram.com/binafanezze/",
            twitter: "",
            facebook: "",
          },
        },
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

p {
  font-size: var(--all_text_size_p);
}

h4 {
  color: var(--primary_gold_color);
  font-size: calc(var(--all_text_size_h5)/0.9);
  text-shadow: var(--all_page_text_shadow);
}

h2 {
  font-size: calc(var(--all_text_size_h2)/1.4);
  font-family: var(--all_text_font_family);
  color: var(--secundary_gray_color);
  margin: 20px;
  opacity: 0;
  transition: opacity 1s;
  text-wrap: nowrap;
}

.row {
  justify-content: center
}

.info-card {
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

  &:hover {
    border: 1px solid white;
  }
}

.card0,
.card1,
.card2,
.card3,
.card4 {
  background: var(--section_team_cards_background_before);
  background-size: var(--section_team_cards_background_size);
  filter: var(--section_team_cards_grayscale_filter);

  &:hover {
    background: var(--section_team_cards_background_after);
    background-size: var(--section_team_cards_background_size_hoover);
    filter: var(--section_team_cards_grayscale_filter);
  }
}

.card0:hover h2,
.card0:hover .fa,
.card1:hover h2,
.card1:hover .fa,
.card2:hover h2,
.card2:hover .fa,
.card3:hover h2,
.card3:hover .fa,
.card4:hover h2,
.card4:hover .fa {
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
  bottom: -5%;
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

  &:hover {
    color: #583f13;
    transform: scale(1.5);
  }
}

.team-member {
  padding-bottom: 10%;
  width: 250px;
  margin: 0vw 2vw 0vw 2vw;
}

@media (max-width: 768px) {

  .team-member {
    width: calc(230px/1.8);
    margin: 0vw 2vw 0vw 2vw;
  }

  .card {
    height: calc(50vh/1.4);
    width: calc(40vh/1.4);
    border-radius: calc(10px/1.4);
  }

  .icons {
    height: calc(130px/1.3);
    bottom: -5%;
    width: calc(50px/1.3);
    padding-bottom: calc(15px/1.3);
  }

  h2 {
    font-size: calc(var(--all_text_size_h2)/2.0);
    text-wrap: nowrap;
  }

  h4 {
    font-size: calc(var(--all_text_size_h3)/1.9);
    text-wrap: nowrap;
  }

  p {
    font-size: calc(var(--all_text_size_p)/1.2);
  }

}

@media (max-width: 575px) {

  .card {
    height: calc(50vh/2);
    width: calc(40vh/2);
    border-radius: calc(10px/2);
  }

  .team-member {
    margin: 0vw 2vw 0vw 2vw;
  }

  .icons {
    height: calc(130px/2.3);
    bottom: 5%;
    width: calc(50px/1.9);
    padding-bottom: calc(15px/1.9);
  }

  h2 {
    font-size: calc(var(--all_text_size_h2)/2.6);
    text-wrap: nowrap;
  }

  h4 {
    font-size: calc(var(--all_text_size_h3)/2.5);
    text-wrap: nowrap;
  }

  p {
    font-size: calc(var(--all_text_size_p)/2.1);
  }
}
</style>