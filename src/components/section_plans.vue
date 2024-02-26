<template>
    <section id="section-plans">
        <div>
            <h2 class="section-heading text-center">Planos</h2>
            <h3 class="section-subheading text-muted text-center">Selecione o plano que melhor se encaixa com o seu empreendimento!</h3>
          <div class="container">
          

<div class="pricing-box-container">
	<div class="pricing-box pricing-box-low text-center">
		<h5>PRIMEIROS PASSOS PRO</h5>
		<p class="price"><sup>R$</sup>1.500<sub>/mês</sub></p>
		<ul class="features-list">
      <li><strong></strong> Anúncio Pago</li>
      <li><strong></strong> Social Media</li>
      <li><strong></strong> Copyright</li>
      <li><strong></strong> Filmmaker</li>
			<li><strong></strong> Plano Estratégico</li>
			<li><strong>21</strong> Stories por semana</li>
			<li><strong>3</strong> Post Feed por semana</li>
			<li><strong>1</strong> Reels por semana</li>
		</ul>
		<button class="btn-primary">Get Started</button>
	</div>

	<div class="pricing-box pricing-box-medium text-center">
		<h5>STRATEGIA MOMENTUM</h5>
		<p class="price"><sup>R$</sup>2.957<sub>/mês</sub></p>
		<ul class="features-list">
			<li><strong></strong> Anúncio Pago</li>
      <li><strong></strong> Social Media</li>
      <li><strong></strong> Copyright</li>
      <li><strong></strong> Filmmaker</li>
			<li><strong></strong> Plano Estratégico</li>
			<li><strong>28</strong> Stories por semana</li>
			<li><strong>3</strong> Post Feed por semana</li>
			<li><strong>2</strong> Reels por semana</li>
		</ul>
		<button class="btn-primary">Get Started</button>
	</div>

	<div class="pricing-box pricing-box-high text-center">
		<h5>SUCESSO SUPREMO</h5>
		<p class="price"><sup>R$</sup>6.450<sub>/mês</sub></p>
		<ul class="features-list">
      <li><strong></strong> Social Media</li>
      <li><strong></strong> Copyright</li>
      <li><strong></strong> Tráfego Pago</li>
			<li><strong></strong> Plano Estratégico</li>
      <li><strong></strong> Design</li>
      <li><strong></strong> Filmmaker</li>
      <li><strong></strong> Storytelling</li>
			<li><strong>35</strong> Stories por semana</li>
			<li><strong>4</strong> Post Feed por semana</li>
			<li><strong>2</strong> Reels por semana</li>
      <li><strong>1</strong> Reels/Storytelling por semana</li>
		</ul>
		<button class="btn-primary">Get Started</button>
	</div>
</div>

    </div>
    </div>
  </section>
</template>

  <script>
export default {
  name: "SectionPlans",
  data() {
    return {
    };
  },
  methods: {
    
  },
};
</script>

<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css');
@import url('https://fonts.googleapis.com/css?family=Open+Sans');

* {
	box-sizing: border-box;
}

body {
	background-color: #f6f5f7;
	font-family: 'Open Sans', sans-serif;
	margin-bottom: 50px;
}

.text-center {
	text-align: center;
	
}
.section-heading{
	color:#d7a449;
	text-shadow: 3px 3px 0 hsl(0, 0%, 0%, 0.25);
}

.pricing-box-container {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-wrap: wrap;
}

.pricing-box {
	background-color: #ffffff;
	box-shadow: 0px 2px 15px 0px rgba(0,0,0,0.5);
	border-radius: 4px;
	flex: 1;
	padding: 0 30px 30px;
	margin: 2%;
	min-width: 250px;
	max-width: 350px;
	transition: box-shadow 0.3s ease-in-out, transform 0.3s ease-in-out;
}

.pricing-box h5 {
	text-transform: uppercase;
}

.price {
	margin: 24px 0;
	font-size: 36px;
	font-weight: 900;
}

.price sub, .price sup {
	font-size: 16px;
	font-weight: 100;
}

.features-list {
	padding: 0;
	list-style-type: none;
}

.features-list li {
	font-weight: 100;
	padding: 1px 0;
	font-weight: 100;
}

.features-list li:not(:last-of-type) {
	border-bottom: 1px solid rgba(0, 0, 0, 0.1);
}

.pricing-box:hover {
  box-shadow: 0px 2px 20px 0px rgba(0,0,0,0.8);
  transform: scale(1.02);
}
.btn-primary {
	border-radius: 25px;
	border: none;
	background-color: #EC1362;
	color: #ffffff;
	cursor: pointer;
	padding: 10px 15px;
	margin-top: 20px;
	text-transform: uppercase;
	transition: all 0.1s ease-in-out;
}

.btn-primary:hover {
	box-shadow: 0px 2px 15px 0px rgba(0,0,0,0.5);
	transform: translateY(-3px);
}

.pricing-box-low {
	background-image: url("src/assets/img/background_plan.png");
	background-size: cover;
	background-position: center center;
	color: #ffffff;
}

.pricing-box-medium {
	background-image: url("src/assets/img/background_plan.png");
	background-size: cover;
	background-position: center center;
	color: #ffffff;
}

.pricing-box-high {
	background-image: url("src/assets/img/background_plan.png");
	background-size: cover;
	background-position: center center;
	color: #ffffff;
}

.pricing-box-bg-image .features-list li {
	border-bottom-color: rgba(255, 255, 255, 1);
}

.pricing-box-bg-image .btn-primary {
	background-color: #ffffff;
	color: #000;
}
</style>