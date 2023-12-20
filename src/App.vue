<template>
	<div id="app">
		<div class="hero-section">
			<div class="about-text hover-target">Sobre</div>
			<div class="contact-text hover-target">Contato</div>
			<div class="section-center">
				<div class="container-fluid">
					<div class="row justify-content-center">
						<header id="page-top">
							<div class="container">
								<div class="intro-text">
									<div class="intro-lead-in">Guiando Sua Marca pela Estrada do Sucesso: Juntos,
										Construímos o Caminho para o Impacto.</div>
									<div class="intro-heading">IZTOIC</div>
									<a class="page-scroll">Maximizar o crescimento de empresas com planos estratégicos de marketing personalizados e altamente eficazes.</a><br>
									<a class="page-scroll">Conheça nosso trabalho!</a>
									<div class="col-12 text-center mt-4 mt-lg-5">
										<p>
											<span class="travel hover-target">Serviços</span>
											<span class="wildlife hover-target">Planos</span>
											<span class="nature hover-target">Portifólio</span>
										</p>
									</div>

								</div>

							</div>
						</header>
					</div>

				</div>
			</div>
			<div class="div-inferior">
				<div class="container">
					<div class="row justify-content-center">
						<div class="col-md-4">
							<span class="copyright">Copyright © Iztoic 2023</span>
						</div>
						<div class="col-md-4">
							<ul class="list-inline social-buttons justify-content-center">
								<li><a href="#"><i class="fa fa-twitter"></i></a></li>
								<li><a href="https://www.instagram.com/iztoic/"><i class="fa fa-instagram"></i></a></li>
								<li><a href="#"><i class="fa fa-linkedin"></i></a></li>
							</ul>
						</div>
						<div class="col-md-4">
							<ul class="list-inline quicklinks">
								<li><a href="#" class="white-and-bold">Politica de Privacidade</a></li>
							</ul>
						</div>
					</div>
				</div>
			</div>
		</div>

		<div class="layerindex about-section">
			<div class="about-close hover-target"></div>
			<SectionAbout />
			<SectionTestimonials />
			<SectionTeam />
		</div>

		<div class="layerindex contact-section">
			<div class="contact-close hover-target"></div>
			<SectionContact />
		</div>

		<div class="travel-section">
			<div class="travel-close hover-target"></div>
			<SectionServices />
		</div>

		<div class="layerindex wildlife-section">
			<div class="wildlife-close hover-target"></div>
			<SectionPlans />
			<SectionBooks />
		</div>

		<div class="nature-section">
			<div class="nature-close hover-target"></div>
			<SectionPortifolio />
		</div>

		<div class='cursor' id="cursor"></div>
		<div class='cursor2' id="cursor2"></div>
		<div class='cursor3' id="cursor3"></div>

		
		<div @click="showHomepage">
    <div v-if="loading" class="loading">
      <div class="loading-progress" :style="{ transform: 'translateX(' + progress + '%)' }"></div>
      <div class="loading-title">
        <LoaderLogo />
      </div>
    </div>
  </div>

	</div>
</template>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.11.2/jquery-ui.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script>
<script src="https://raw.githubusercontent.com/IronSummitMedia/startbootstrap/gh-pages/templates/agency/js/bootstrap.min.js"></script>
<script>
import SectionAbout from './components/section_about.vue';
import SectionTeam from './components/section_team.vue';
import SectionContact from './components/section_contact.vue';
import SectionTestimonials from './components/section_testimonials.vue';
import SectionServices from './components/section_services.vue';
import SectionPlans from './components/section_plans.vue';
import SectionPortifolio from './components/section_portifolio.vue';
import SectionBooks from './components/section_books.vue';
import LoaderLogo from './components/loader_logo.vue';
export default {
	name: 'app',
	components: {
		SectionAbout,
		SectionTeam,
		SectionContact,
		SectionTestimonials,
		SectionServices,
		SectionPortifolio,
		SectionPlans,
		SectionBooks,
		LoaderLogo,
	},

	data() {
    return {
      loading: true,
      progress: 0,
	  
    };
  },

  methods: {
    simulateLoader() {
      const loaderInterval = setInterval(() => {
        this.progress += this.getRandomArbitrary(10, 25);

        if (this.progress >= 75) {
          clearInterval(loaderInterval);
          this.progress = 100;

          // Adicione um pequeno atraso antes de esconder o loader
          setTimeout(() => {
            this.showHomepage();
          }, 7000);
        }
      }, this.getRandomArbitrary(100, 500));
    },
    getRandomArbitrary(min, max) {
      return Math.random() * (max - min) + min;
    },
    showHomepage() {
      this.loading = false;
    },
  },

	mounted() {
		this.simulateLoader();

		document.addEventListener("DOMContentLoaded", function () {
			// Page cursors
			var cursor = document.getElementById("cursor");
			var cursor2 = document.getElementById("cursor2");
			var cursor3 = document.getElementById("cursor3");

			document.body.addEventListener("mousemove", function (event) {
				cursor.style.left = event.clientX + "px";
				cursor.style.top = event.clientY + "px";
				cursor2.style.left = event.clientX + "px";
				cursor2.style.top = event.clientY + "px";
				cursor3.style.left = event.clientX + "px";
				cursor3.style.top = event.clientY + "px";
			});

			function addHover() {
				cursor2.classList.add("hover");
				cursor3.classList.add("hover");
			}

			function removeHover() {
				cursor2.classList.remove("hover");
				cursor3.classList.remove("hover");
			}

			removeHover();

			var hoverTargets = document.querySelectorAll(".hover-target");

			hoverTargets.forEach(function (element) {
				element.addEventListener("mouseover", addHover);
				element.addEventListener("mouseout", removeHover);
			});

			// About page
			var aboutText = document.querySelector(".about-text");
			var aboutClose = document.querySelector(".about-close");

			aboutText.addEventListener("click", function () {
				document.body.classList.add("about-on");
			});

			aboutClose.addEventListener("click", function () {
				document.body.classList.remove("about-on");
			});

			// Contact page
			var contactText = document.querySelector(".contact-text");
			var contactClose = document.querySelector(".contact-close");

			contactText.addEventListener("click", function () {
				document.body.classList.add("contact-on");
			});

			contactClose.addEventListener("click", function () {
				document.body.classList.remove("contact-on");
			});

			// Travel portfolio page
			var travel = document.querySelector(".travel");
			var travelClose = document.querySelector(".travel-close");

			travel.addEventListener("click", function () {
				document.body.classList.add("travel-on");
			});

			travelClose.addEventListener("click", function () {
				document.body.classList.remove("travel-on");
			});

			// Wildlife portfolio page
			var wildlife = document.querySelector(".wildlife");
			var wildlifeClose = document.querySelector(".wildlife-close");

			wildlife.addEventListener("click", function () {
				document.body.classList.add("wildlife-on");
			});

			wildlifeClose.addEventListener("click", function () {
				document.body.classList.remove("wildlife-on");
			});

			// Nature portfolio page
			var nature = document.querySelector(".nature");
			var natureClose = document.querySelector(".nature-close");

			nature.addEventListener("click", function () {
				document.body.classList.add("nature-on");
			});

			natureClose.addEventListener("click", function () {
				document.body.classList.remove("nature-on");
			});
		});

		
	},
};
</script>

<style scoped>
@import url('https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css');
@import url('https://fonts.googleapis.com/css?family=Poppins:100,100i,200,200i,300,300i,400,400i,500,500i,600,600i,700,700i,800,800i,900,900i');
@import url('https://fonts.googleapis.com/css?family=Dancing+Script:400,700');
@import url('https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.3/css/bootstrap.min.css');
@import url('https://startbootstrap.com/templates/agency/font-awesome-4.1.0/css/font-awesome.min.css');
@import url('https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css');
@import url('https://ajax.googleapis.com/ajax/libs/jqueryui/1.11.2/themes/smoothness/jquery-ui.css');

body {
	font-family: 'Poppins', sans-serif;
	font-weight: 300;
	font-size: 15px;
	line-height: 1.6;
	color: #fff;
	background-color: #1f2029;
	overflow: hidden;
	height: 100vh;
	-webkit-transition: all 300ms linear;
	transition: all 300ms linear;
	perspective: 800px;
}

a {
	cursor: pointer;
}

a:hover {
	text-decoration: none;
}

::selection {
	color: #c4c3ca;
	background-color: #000;
}

::-moz-selection {
	color: #c4c3ca;
	background-color: #000;
}

/* #Cursor
================================================== */

.cursor,
.cursor2,
.cursor3 {
	position: fixed;
	border-radius: 50%;
	transform: translateX(-50%) translateY(-50%);
	pointer-events: none;
	left: -100px;
	top: 50%;
	mix-blend-mode: difference;
	-webkit-transition: all 300ms linear;
	transition: all 300ms linear;
}

.cursor {
	background-color: #fff;
	height: 0;
	width: 0;
	z-index: 99999;
}

.cursor2,
.cursor3 {
	height: 36px;
	width: 36px;
	z-index: 99998;
	-webkit-transition: all 0.3s ease-out;
	transition: all 0.3s ease-out
}

.cursor2.hover,
.cursor3.hover {
	-webkit-transform: scale(2) translateX(-25%) translateY(-25%);
	transform: scale(2) translateX(-25%) translateY(-25%);
	border: none
}

.cursor2.hover {
	background: rgba(255, 255, 255, 1);
	border-color: transparent;
}

@media screen and (max-width: 1200px) {

	.cursor,
	.cursor2,
	.cursor3 {
		display: none
	}
}

/* #Primary style
================================================== */

.hero-section {
	position: relative;
	width: 100%;
	display: block;
	overflow: hidden;
	height: 100vh;
	background-image: url(https://unsplash.imgix.net/uploads%2F14115408840644deb16b0%2F2dc933e3?q=75&fm=jpg&auto=format&s=7f43646e4d26049c6c39890afb2e5ced);
	background-size: cover;
	background-position: center;
	transform: scale(1) rotateX(0);
	box-shadow: 0 0 40px rgba(0, 0, 0, 0.2);
	-webkit-transition: all 300ms linear;
	transition: all 300ms linear;
	-webkit-transition-delay: 400ms;
	transition-delay: 400ms;
	transform-origin: center top;
}

.hero-section h1 {
	color: #fff;
	font-size: 5vw;
	line-height: 1;
	font-weight: 900;
}

.hero-section .dancing {
	font-family: 'Dancing Script', cursive;
	letter-spacing: 1px;
	color: #866BAF;
	font-size: 26px;
	line-height: 1;
	font-weight: 700;
}

@media screen and (max-width: 580px) {
	.hero-section .dancing {
		font-size: 18px;
	}
}

.hero-section p {
	font-size: 15px;
	line-height: 20px;
	font-weight: 500;
	color: #fff;
	letter-spacing: 1px;
}

.hero-section p span {
	margin-left: 15px;
	margin-right: 15px;
	position: relative;
	display: inline-block;
	cursor: pointer;
	padding-bottom: 35px;
}

.hero-section p span:before {
	position: absolute;
	content: '';
	bottom: 10px;
	left: 50%;
	height: 30px;
	width: 30px;
	margin-left: -15px;
	z-index: -1;
	background-repeat: no-repeat;
	background-position: center;
	background-size: 30px 30px;
	background-image: url('http://www.ivang-design.com/svg-load/portfolio/down.svg');
	opacity: 0.2;
	-webkit-transition: all 200ms linear;
	transition: all 200ms linear;
}

.hero-section p span:hover:before {
	opacity: 1;
	bottom: 5px;
}

body.about-on .hero-section {
	transform: scale(0.75);
	-webkit-transition-delay: 0ms;
	transition-delay: 0ms;
}

body.contact-on .hero-section {
	transform: scale(0.75);
	-webkit-transition-delay: 0ms;
	transition-delay: 0ms;
}

body.travel-on .hero-section {
	transform: rotateX(-10deg);
	-webkit-transition-delay: 0ms;
	transition-delay: 0ms;
}

body.wildlife-on .hero-section {
	transform: rotateX(-10deg);
	-webkit-transition-delay: 0ms;
	transition-delay: 0ms;
}

body.nature-on .hero-section {
	transform: rotateX(-10deg);
	-webkit-transition-delay: 0ms;
	transition-delay: 0ms;
}

.about-text {
	position: absolute;
	font-size: 17px;
	line-height: 20px;
	font-weight: 700;
	color: #fff;
	letter-spacing: 2px;
	top: 50%;
	left: 40px;
	cursor: pointer;
	z-index: 2;
	-webkit-writing-mode: vertical-lr;
	writing-mode: vertical-lr;
	transform: translateY(-50%);
	-webkit-transition: all 200ms linear;
	transition: all 200ms linear;
}

.about-text:before {
	position: absolute;
	content: '';
	top: 50%;
	left: -25px;
	height: 30px;
	width: 30px;
	margin-top: -15px;
	z-index: -1;
	background-repeat: no-repeat;
	background-position: center;
	background-size: 30px 30px;
	background-image: url('http://www.ivang-design.com/svg-load/portfolio/left.svg');
	opacity: 0.2;
	-webkit-transition: all 200ms linear;
	transition: all 200ms linear;
}

.about-text:hover:before {
	opacity: 1;
	left: -30px;
}

.about-section {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	display: block;
	overflow: hidden;
	height: 100vh;
	background-color: rgba(31, 32, 41, 1);
	transform: translateX(-100%);
	-webkit-transition: all 300ms linear;
	transition: all 300ms linear;
	z-index: 10;
}

body.about-on .about-section {
	transform: translateX(0);
	-webkit-transition-delay: 400ms;
	transition-delay: 400ms;
}

.about-close {
	position: absolute;
	top: 20px;
	right: 20px;
	width: 30px;
	display: block;
	overflow: hidden;
	height: 30px;
	-webkit-transition: all 200ms linear;
	transition: all 200ms linear;
	background-repeat: no-repeat;
	background-position: center;
	background-size: 36px 36px;
	background-image: url('http://www.ivang-design.com/svg-load/portfolio/close.svg');
	cursor: pointer;
	z-index: 11;
}

.about-close:hover {
	transform: rotate(90deg);
}

.section-center {
	position: absolute;
	width: 100%;
	left: 0;
	top: 50%;
	transform: translateY(-50%);
	z-index: 1;
}

.about-section img {
	width: 100px;
	height: 100px;
	border-radius: 4px;
	display: block;
	margin: 0 auto;
	box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}

.about-section p span {
	font-family: 'Dancing Script', cursive;
	letter-spacing: 1px;
	color: #866BAF;
	font-size: 25px;
	font-weight: 400;
}

.contact-text {
	position: absolute;
	font-size: 17px;
	line-height: 20px;
	font-weight: 700;
	color: #fff;
	letter-spacing: 2px;
	top: 50%;
	right: 40px;
	cursor: pointer;
	z-index: 2;
	-webkit-writing-mode: vertical-lr;
	writing-mode: vertical-lr;
	transform: translateY(-50%) rotate(180deg);
	-webkit-transition: all 200ms linear;
	transition: all 200ms linear;
}

.contact-text:before {
	position: absolute;
	content: '';
	top: 50%;
	left: -25px;
	height: 30px;
	width: 30px;
	margin-top: -15px;
	z-index: -1;
	background-repeat: no-repeat;
	background-position: center;
	background-size: 30px 30px;
	background-image: url('http://www.ivang-design.com/svg-load/portfolio/left.svg');
	opacity: 0.2;
	-webkit-transition: all 200ms linear;
	transition: all 200ms linear;
}

.contact-text:hover:before {
	opacity: 1;
	left: -30px;
}

.contact-section {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	display: block;
	overflow: hidden;
	height: 100vh;
	background-color: rgba(31, 32, 41, 1);
	transform: translateX(100%);
	-webkit-transition: all 300ms linear;
	transition: all 300ms linear;
	z-index: 10;
}

body.contact-on .contact-section {
	transform: translateX(0);
	-webkit-transition-delay: 400ms;
	transition-delay: 400ms;
}

.contact-close {
	position: absolute;
	top: 20px;
	right: 20px;
	width: 30px;
	display: block;
	overflow: hidden;
	height: 30px;
	-webkit-transition: all 200ms linear;
	transition: all 200ms linear;
	background-repeat: no-repeat;
	background-position: center;
	background-size: 36px 36px;
	background-image: url('http://www.ivang-design.com/svg-load/portfolio/close.svg');
	cursor: pointer;
	z-index: 11;
}

.contact-close:hover {
	transform: rotate(90deg);
}

.contact-section a {
	margin: 0 auto;
	font-size: 32px;
	font-weight: 900;
	letter-spacing: 1px;
	color: #fff;
	display: inline-block;
}

.contact-section .social a {
	margin-left: 8px;
	margin-right: 8px;
	font-size: 15px;
	font-weight: 600;
	letter-spacing: 1px;
	color: #866BAF;
}

@media screen and (max-width: 580px) {
	.contact-section a {
		font-size: 17px;
	}

	.contact-section .social a {
		margin-left: 3px;
		margin-right: 3px;
		font-size: 13px;
		letter-spacing: 0;
	}
}

.travel-section,
.wildlife-section,
.nature-section {
	position: fixed;
	top: 100%;
	left: 0;
	width: 100%;
	height: 100vh;
	display: flex;
	flex-direction: column;
	justify-content: flex-start;
	align-items: center;
	background-color: rgba(31, 32, 41, 1);
	-webkit-transition: all 300ms linear;
	transition: all 300ms linear;
	z-index: 10;
}

.travel-close,
.wildlife-close,
.nature-close {
	position: absolute;
	top: 20px;
	right: 20px;
	width: 30px;
	display: block;
	overflow: hidden;
	height: 30px;
	-webkit-transition: all 200ms linear;
	transition: all 200ms linear;
	background-repeat: no-repeat;
	background-position: center;
	background-size: 36px 36px;
	background-image: url('http://www.ivang-design.com/svg-load/portfolio/close.svg');
	cursor: pointer;
	z-index: 11;
}

.travel-close:hover,
.wildlife-close:hover,
.nature-close:hover {
	transform: rotate(90deg);
}

body.travel-on .travel-section {
	top: 0;
	-webkit-transition-delay: 400ms;
	transition-delay: 400ms;
}

body.wildlife-on .wildlife-section {
	top: 0;
	-webkit-transition-delay: 400ms;
	transition-delay: 400ms;
}

body.nature-on .nature-section {
	top: 0;
	-webkit-transition-delay: 400ms;
	transition-delay: 400ms;
}

.travel-section img,
.wildlife-section img,
.nature-section img {
	margin-top: 30px;
	width: 100%;
	height: auto;
	display: block;
	border-radius: 4px;
	box-shadow: 0 0 20px rgba(0, 0, 0, 0.4);
}

.travel-section h3,
.wildlife-section h3,
.nature-section h3 {
	font-size: 44px;
	line-height: 1.3;
	font-weight: 700;
	letter-spacing: 1px;
	color: #fff;
}

.travel-section p,
.wildlife-section p,
.nature-section p {
	font-size: 14px;
	line-height: 1.7;
	letter-spacing: 1px;
}

.travel-section p span,
.wildlife-section p span,
.nature-section p span {
	font-size: 20px;
	line-height: 1.3;
	font-weight: 700;
	color: #866BAF;
}

.layerindex {
	overflow-y: auto;
}

header {
	text-align: center;
	color: #fff;
	background-attachment: scroll;
	background-position: center center;
	background-repeat: none;
	-webkit-background-size: cover;
	-moz-background-size: cover;
	background-size: cover;
	-o-background-size: cover;
}

header .intro-text {
	padding-top: 100px;
	padding-bottom: 50px;
}

header .intro-text .intro-lead-in {
	margin-bottom: 25px;
	font-family: "Droid Serif", "Helvetica Neue", Helvetica, Arial, sans-serif;
	font-size: 22px;
	font-style: italic;
	line-height: 22px;
}

header .intro-text .intro-heading {
	margin-bottom: 25px;
	text-transform: uppercase;
	font-family: Montserrat, "Helvetica Neue", Helvetica, Arial, sans-serif;
	font-size: 50px;
	font-weight: 700;
	line-height: 50px;
}

@media(min-width:768px) {
	header .intro-text {
		padding-top: 300px;
		padding-bottom: 200px;
	}

	header .intro-text .intro-lead-in {
		margin-bottom: 25px;
		font-family: "Droid Serif", "Helvetica Neue", Helvetica, Arial, sans-serif;
		font-size: 40px;
		font-style: italic;
		line-height: 40px;
	}

	header .intro-text .intro-heading {
		margin-bottom: 50px;
		text-transform: uppercase;
		font-family: Montserrat, "Helvetica Neue", Helvetica, Arial, sans-serif;
		font-size: 75px;
		font-weight: 700;
		line-height: 75px;
	}
}

.btn-xl {
	padding: 20px 40px;
	border-color: #1ee2e7;
	border-radius: 3px;
	text-transform: uppercase;
	font-family: Montserrat, "Helvetica Neue", Helvetica, Arial, sans-serif;
	font-size: 18px;
	font-weight: 700;
	color: #fff;
	background-color: #1ee2e7;
}

.btn-xl:hover,
.btn-xl:focus,
.btn-xl:active,
.btn-xl.active,
.open .dropdown-toggle.btn-xl {
	border-color: #17d0d5;
	color: #fff;
	background-color: #17d0d5;
}

.btn-xl:active,
.btn-xl.active,
.open .dropdown-toggle.btn-xl {
	background-image: none;
}

.btn-xl.disabled,
.btn-xl[disabled],
fieldset[disabled] .btn-xl,
.btn-xl.disabled:hover,
.btn-xl[disabled]:hover,
fieldset[disabled] .btn-xl:hover,
.btn-xl.disabled:focus,
.btn-xl[disabled]:focus,
fieldset[disabled] .btn-xl:focus,
.btn-xl.disabled:active,
.btn-xl[disabled]:active,
fieldset[disabled] .btn-xl:active,
.btn-xl.disabled.active,
.btn-xl[disabled].active,
fieldset[disabled] .btn-xl.active {
	border-color: #1ee2e7;
	background-color: #1ee2e7;
}

.btn-xl .badge {
	color: #fed136;
	background-color: #fff;
}

footer {
	padding: 25px 0;
	text-align: center;
}

span.copyright {
	text-transform: uppercase;
	text-transform: none;
	font-family: Montserrat, "Helvetica Neue", Helvetica, Arial, sans-serif;
	line-height: 40px;
	color: #fff !important;
}

ul.quicklinks {
	margin-bottom: 0;
	text-transform: uppercase;
	text-transform: none;
	font-family: Montserrat, "Helvetica Neue", Helvetica, Arial, sans-serif;
	line-height: 40px;
}

ul.social-buttons {
	margin-bottom: 0;
}

ul.social-buttons li a {
	display: block;
	width: 40px;
	height: 40px;
	border-radius: 100%;
	font-size: 20px;
	line-height: 40px;
	outline: 0;
	color: #fff;
	background-color: #222;
	-webkit-transition: all .3s;
	-moz-transition: all .3s;
	transition: all .3s;
}

ul.social-buttons li a:hover,
ul.social-buttons li a:focus,
ul.social-buttons li a:active {
	background-color: #1ee2e7;
}

.btn:focus,
.btn:active,
.btn.active,
.btn:active:focus {
	outline: 0;
}

.row {
	align-items: center
}

.div-inferior {
	position: fixed;
	bottom: 0;
	left: 0;
	width: 100%;
	display: flex;
	justify-content: center;
	align-items: center;
	padding: 20px;
	z-index: 1000;
}

.social-buttons {
	text-align: center;
}

.div-inferior .container {
	width: 100%;
}

.col-md-4 {
	display: flex;
	justify-content: center;
}

.white-and-bold {
	color: #fff !important;
}
.loading {
  position: fixed;
  height: 100%;
  width: 100%;
  top: 0px;
  left: 0;
  background: #000;
  transition: background-color 0.75s;
  z-index: 1000;
}

.loading-title {
  color: #fff;
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.loading-progress {
  height: 11px;
  background: #0ae741;
  top: 0px;
  bottom: 0;
  width: 100%;
  position: absolute;
  transition: 0.45s;
}
</style>
