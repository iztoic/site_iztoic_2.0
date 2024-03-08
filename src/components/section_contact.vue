<template>
  <div>
    <section id="section-contact">
      <h3 class="title-text-center">Contato</h3>
      <div class="contact-wrapper">
          <form id="contact-form" class="form-horizontal" role="form" action="https://formspree.io/f/xbjnynng" method="POST">
          <div class="form-group">
            <div class="col-sm-12">
              <input type="text" class="form-control" v-model="formData.name" placeholder="NOME" name="name" required>
            </div>
          </div>
          <div class="form-group">
            <div class="col-sm-12">
              <input type="email" class="form-control" v-model="formData.email" placeholder="EMAIL" name="email" required>
            </div>
          </div>
          <textarea class="form-control" rows="10" v-model="formData.message" placeholder="MENSAGEM" name="message" required></textarea>
          <button class="btn btn-primary send-button" id="submit" type="submit" value="SEND">
            <div class="alt-send-button">
              <i class="fa fa-paper-plane"></i><span class="send-text">ENVIAR</span>
            </div>
          </button>
        </form>
        <div class="direct-contact-container">
          <ul class="contact-list">
            <li class="list-item"><i class="fa fa-map-marker fa-2x"><span class="contact-text place">{{ contactInfo.location }}</span></i></li>
            <li class="list-item"><i class="fa fa-phone fa-2x"><span class="contact-text phone"><a :href="'tel:' + contactInfo.phone" >{{ contactInfo.phone }}</a></span></i></li>
            <li class="list-item"><i class="fa fa-envelope fa-2x"><span class="contact-text gmail"><a :href="'mailto:' + contactInfo.email" >{{ contactInfo.email }}</a></span></i></li>
          </ul>
          <hr>
          <ul class="social-media-list">
            <li onclick="window.open('https://www.linkedin.com/company/iztoic', '_blank');"><a class="contact-icon"><i class="fa fa-linkedin" aria-hidden="true"></i></a></li>
            <li onclick="window.open('https://www.instagram.com/iztoic', '_blank');"><a class="contact-icon"><i class="fa fa-instagram" aria-hidden="true"></i></a></li>
          </ul>
          <hr>
          <div class="copyright">&copy; TODOS OS DIREITOS RESERVADOS</div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "SectionContact",
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      },
      contactInfo: {
        location: "Joinville, SC",
        phone: "(47) 99717-2238",
        email: "contato@iztoic.com",
        linkedin: "https://www.instagram.com/iztoic",
        instagram: "https://www.instagram.com/iztoic"
      }
    };
  },
  methods: {
    submitForm() {
      this.formData.name = '';
      this.formData.email = '';
      this.formData.message = '';
      this.$emit('form-submitted');
    }
  }
}
</script>
    
<style scoped>
.title-text-center{
  text-align: center;
  color: var(--primary_gold_color);
  text-shadow: var(--all_page_text_shadow);
  font-size: var(--all_text_size_h3);
}

.contact-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 0 auto;
  padding: 20px;
  position: relative;
  max-width: 840px;
}

/* Left contact page */
.form-horizontal {
  /*float: left;*/
  max-width: 400px;
  font-family: 'Lato';
  font-weight: 400;
}

.form-control,
textarea {
  max-width: 400px;
  background-color: #000;
  color: #d7a449;
  letter-spacing: 1px;
}

.send-button {
  margin-top: 15px;
  height: 34px;
  width: 400px;
  overflow: hidden;
  transition: all .2s ease-in-out;
}

.alt-send-button {
  width: 400px;
  height: 34px;
  transition: all .2s ease-in-out;
}

.send-text {
  display: block;
  margin-top: 10px;
  font: 700 12px 'Lato', sans-serif;
  letter-spacing: 2px;
}

.alt-send-button:hover {
  transform: translate3d(0px, -29px, 0px);
}

/* Begin Right Contact Page */
.direct-contact-container {
  max-width: 400px;
}

/* Location, Phone, Email Section */
.contact-list {
  list-style-type: none;
  margin-left: -30px;
  padding-right: 20px;
}

.list-item {
  line-height: 4;
  color: #d7a449;
}

.contact-text {
  font: 300 18px 'Lato', sans-serif;
  letter-spacing: 1.9px;
  color: #fff;
}

.place {
  margin-left: 62px;
  white-space: nowrap;
}

.phone {
  margin-left: 56px;
  white-space: nowrap;
}

.gmail {
  margin-left: 53px;
  white-space: nowrap;
}

.contact-text a {
  color: #fff;
  text-decoration: none;
  transition-duration: 0.2s;
}

.contact-text a:hover {
  color: #d7a449;
  text-decoration: none;
}


/* Social Media Icons */
.social-media-list {
  position: relative;
  font-size: 22px;
  text-align: center;
  width: 100%;
  margin: 0 auto;
  padding: 0;
}

.social-media-list li a {
  color: #d7a449;
}

.social-media-list li {
  position: relative;
  display: inline-block;
  height: 60px;
  width: 60px;
  margin: 10px 3px;
  line-height: 60px;
  border-radius: 50%;
  color: #d7a449;
  background-color: rgb(27, 27, 27);
  cursor: pointer;
  transition: all .2s ease-in-out;
}

.social-media-list li:after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 60px;
  height: 60px;
  line-height: 60px;
  border-radius: 50%;
  opacity: 0;
  box-shadow: 0 0 0 1px #fff;
  transition: all .2s ease-in-out;
}

.social-media-list li:hover {
  background-color: #fff;
}

.social-media-list li:hover:after {
  opacity: 1;
  transform: scale(1.12);
  transition-timing-function: cubic-bezier(0.37, 0.74, 0.15, 1.65);
}

.social-media-list li:hover a {
  color: #000;
}

.copyright {
  font: 200 14px 'Oswald', sans-serif;
  color: #d7a449;
  letter-spacing: 1px;
  text-align: center;
}

hr {
  border-color: rgba(255, 255, 255, .6);
}

@media screen and (max-width: 850px) {
  .contact-wrapper {
    flex-direction: column;
    align-items: center;
  }

  .form-horizontal {
    max-width: 300px;
  }

  .direct-contact-container {
    max-width: 300px;
    margin-top: 40px;
  }
  .send-button {
    width: 100%;
  }
  .col-sm-12{
  margin: 0px 20vw 0 0;
  }
  .alt-send-button {
    width: 100%;
  }
}

@media screen and (max-width: 569px) {
  .form-control,
  textarea {
    width: 100%;
  }
  .col-sm-12{
  margin: 0px 20vw 0 0;
  }

  .form-group {
    margin-bottom: 20px;
  }

  .social-media-list li {
    height: 50px;
    width: 50px;
    line-height: 50px;
    font-size: 1.8rem;
  }

  .social-media-list li:after {
    width: 50px;
    height: 50px;
    line-height: 50px;
  }

  .send-text {
    margin-top: 6px; /* Ajuste o espaçamento conforme necessário */
  }
}

@media screen and (max-width: 410px) {
  .alt-send-button {
    width: 100%;
  }
  .col-sm-12{
  margin: 0px 20vw 0 0;
  }
  .send-text {
    font-size: 14px; /* Ajuste o tamanho da fonte conforme necessário */
  }
}
</style>