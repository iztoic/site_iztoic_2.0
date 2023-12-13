<template>
  <div id="app">
    <div class="hero-section">	
		<div class="about-text hover-target">about</div>
		<div class="contact-text hover-target">contact</div>
		<div class="section-center">
			<div class="container-fluid">
				<div class="row justify-content-center">
					<div class="col-12 text-center">
						<h1>Christian Arete</h1>
					</div>
					<div class="col-12 text-center mb-2">
						<div class="dancing">photography</div>
					</div>
					<div class="col-12 text-center mt-4 mt-lg-5">
						<p>
							<span class="travel hover-target">travel</span> 
							<span class="wildlife hover-target">wildlife</span> 
							<span class="nature hover-target">nature</span>
						</p>
					</div>
				</div>
			</div>
		</div>
	</div>	
	
	<div class="layerindex about-section">
    <div class="about-close hover-target"></div>
    <SectionAbout/>
    <SectionTeam/>
	</div>
	
	<div class="contact-section">	
		<div class="contact-close hover-target"></div>
		<div class="section-center">
			<div class="container">
				<div class="row justify-content-center">
					<div class="col-12 text-center">
						<a href="#" class="hover-target">arete@photography.com</a>
					</div>
					<div class="col-12 text-center social mt-4">
						<a href="#" class="hover-target">instagram</a>
						<a href="#" class="hover-target">flickr</a>
						<a href="#" class="hover-target">facebook</a>
					</div>
				</div>
			</div>
		</div>
	</div>
	
	<div class="travel-section">	
		<div class="travel-close hover-target"></div>
		<div class="container">
			<div class="row justify-content-center">
				<div class="col-12 text-center">
					<h3>travel</h3>
				</div>
				<div class="col-12 mt-3 text-center">
					<p><span>Canon PowerShot S95</span></p>
				</div>
				<div class="col-12 text-center">
					<p>
						focal length: 22.5mm<br>
						aperture: ƒ/5.6<br>
						exposure time: 1/1000<br>
						ISO: 80
					</p>
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
			</div>
		</div>
	</div>
	
	<div class="wildlife-section">	
		<div class="wildlife-close hover-target"></div>
		<div class="container">
			<div class="row justify-content-center">
				<div class="col-12 text-center">
					<h3>wildlife</h3>
				</div>
				<div class="col-12 mt-3 text-center">
					<p><span>Canon PowerShot S95</span></p>
				</div>
				<div class="col-12 text-center">
					<p>
						focal length: 22.5mm<br>
						aperture: ƒ/5.6<br>
						exposure time: 1/1000<br>
						ISO: 80
					</p>
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
			</div>
		</div>
	</div>
	
	<div class="nature-section">	
		<div class="nature-close hover-target"></div>
		<div class="container">
			<div class="row justify-content-center">
				<div class="col-12 text-center">
					<h3>nature</h3>
				</div>
				<div class="col-12 mt-3 text-center">
					<p><span>Canon PowerShot S95</span></p>
				</div>
				<div class="col-12 text-center">
					<p>
						focal length: 22.5mm<br>
						aperture: ƒ/5.6<br>
						exposure time: 1/1000<br>
						ISO: 80
					</p>
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
				<div class="col-md-6 col-lg-4">
					<img src="http://www.ivang-design.com/svg-load/portfolio/photo-p.jpg" alt="">
				</div>
			</div>
		</div>
	</div>
	
	<div class='cursor' id="cursor"></div>
	<div class='cursor2' id="cursor2"></div>
	<div class='cursor3' id="cursor3"></div>

<!-- Link to page
================================================== -->

<a href="https://front.codes/" class="link-to-portfolio hover-target" target=”_blank”></a>
  </div>
</template>


<script>
import SectionAbout from './components/section_about.vue';
import SectionTeam from './components/section_team.vue';
export default {
  name: 'app',
  components: {
    SectionAbout,
    SectionTeam,
  },
  
  mounted() {
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
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Poppins:100,100i,200,200i,300,300i,400,400i,500,500i,600,600i,700,700i,800,800i,900,900i');
@import url('https://fonts.googleapis.com/css?family=Dancing+Script:400,700');
@import url('https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.3/css/bootstrap.min.css');

body{
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
.cursor3{
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
.cursor{
	background-color: #fff;
	height: 0;
	width: 0;
	z-index: 99999;
}
.cursor2,.cursor3{
	height: 36px;
	width: 36px;
	z-index:99998;
	-webkit-transition:all 0.3s ease-out;
	transition:all 0.3s ease-out
}
.cursor2.hover,
.cursor3.hover{
	-webkit-transform:scale(2) translateX(-25%) translateY(-25%);
	transform:scale(2) translateX(-25%) translateY(-25%);
	border:none
}
.cursor2.hover{
	background: rgba(255,255,255,1);
	border-color: transparent;
}

@media screen and (max-width: 1200px){
	.cursor,.cursor2,.cursor3{
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
	background-image: url('http://www.ivang-design.com/svg-load/portfolio/photo.jpg');
	background-size: cover;
	background-position: center;
	transform: scale(1) rotateX(0);
	box-shadow: 0 0 40px rgba(0,0,0,0.2);
	-webkit-transition: all 300ms linear;
	transition: all 300ms linear;
	-webkit-transition-delay: 400ms;
	transition-delay: 400ms;
	transform-origin: center top;
}
.hero-section h1{
    color: #fff;
	font-size: 5vw;
	line-height: 1;
	font-weight: 900;
}
.hero-section .dancing{
    font-family: 'Dancing Script', cursive;
	letter-spacing: 1px;
	color: #866BAF;
	font-size: 26px;
	line-height: 1;
	font-weight: 700;
}
@media screen and (max-width: 580px){
	.hero-section .dancing{
		font-size: 18px;
	}
}
.hero-section p{
	font-size: 15px;
	line-height: 20px;
	font-weight: 500;
	color: #fff;
	letter-spacing: 1px;
}
.hero-section p span{
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
	background-color: rgba(31,32,41,1);
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
	box-shadow: 0 0 20px rgba(0,0,0,0.15);
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
	background-color: rgba(31,32,41,1);
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
.contact-section a{
    margin: 0 auto;
	font-size: 32px;
	font-weight: 900;
	letter-spacing: 1px;
	color: #fff;
  display: inline-block;
}
.contact-section .social a{
    margin-left: 8px;
	margin-right: 8px;
	font-size: 15px;
	font-weight: 600;
	letter-spacing: 1px;
	color: #866BAF;
}
@media screen and (max-width: 580px){
	.contact-section a{
		font-size: 17px;
	}
	.contact-section .social a{
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
	padding: 100px 0;
	width: 100%;
	height: 100vh;
	display: block;
	overflow-x: hidden;
	overflow-y: auto;
	background-color: rgba(31,32,41,1);
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
	box-shadow: 0 0 20px rgba(0,0,0,0.4);
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

.layerindex{
  overflow-y: auto;
}
</style>
