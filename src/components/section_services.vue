<template>
  <div>
    <section id="section-services">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 text-center">
            <h2 class="section-heading">Serviços</h2>
            <h3 class="section-subheading text-muted">Verifique as opções.</h3>
          </div>
        </div>
        <div class="row text-center">
          <div class="col-md-3 service-item">
            <span class="fa-stack fa-4x">
              <img src="https://www.yudiz.com/codepen/photography-banner/VFX.png" class="fa fa-stack-1x copyright rounded-circle" alt="Imagem" />
            </span>
            <h4 class="service-heading">Copyright</h4>
            <p class="text-muted">
              O copyright, muitas vezes conhecido como "copy", é a arte de desenvolver textos persuasivos que cativam o publico e o levam a tomar a ação. É a linguagem que vende produtos, idéias e histórias.
            </p>
          </div>
          <div class="col-md-3 service-item">
            <span class="fa-stack fa-4x">
              <img src="https://www.yudiz.com/codepen/photography-banner/Videography.png" class="fa fa-stack-1x video-maker rounded-circle" alt="Imagem" />
            </span>
            <h4 class="service-heading">Video Maker</h4>
            <p class="text-muted">
              O Video Maker é o Profissional da produção de videos, que contam histórias de forma vizual e envolvente. O video se tornou uma ferramenta de comunicação primordial, e sua produção envolve a criação de conteudo impactante, atraindo a atenção do publico.
            </p>
          </div>
          <div class="col-md-3 service-item">
            <span class="fa-stack fa-4x">
              <img src="https://www.yudiz.com/codepen/photography-banner/photography.png" class="fa fa-stack-1x social-media rounded-circle" alt="Imagem" />
            </span>
            <h4 class="service-heading">Social Media</h4>
            <p class="text-muted">
              As redes sociais desempenham um papel criticona construção e manutenção do publico. Os profissionais de Social Media são especialistas em gerenciar a presença de uma marca em plataformas como Instagram e Facebook.
            </p>
          </div>
          <div class="col-md-3 service-item">
            <span class="fa-stack fa-4x">
              <img src="https://www.yudiz.com/codepen/photography-banner/photography.png" class="fa fa-stack-1x marketing-digital rounded-circle" alt="Imagem" />
            </span>
            <h4 class="service-heading">Marketing Digital</h4>
            <p class="text-muted">
              O Marketing Digital é o guarda-chuva sob o qual todas essas disciplinas se reunem. Ele abrange estratégias e táticas para promover e comercializar produtos ou serviços online. Desde anuncios pagos e otimização de mecanismos de busca até o uso eficaz de redes sociais, o marketing digital envolve a criação de estratégias que maximizam a visibilidade e o alcance online.
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
    name: "SectionServices"
};
</script>

<style scoped>
body {
  font-family: 'Arial', sans-serif;
  color: #333; /* Cor do texto */
}

.container {
  padding: 40px 0; /* Espaçamento interno para os elementos dentro do container */
}

.section-heading {
  color:#d7a449; /* Cor do título principal */
  text-shadow: 3px 3px 0 hsl(0, 0%, 0%, 0.25);
}

.section-subheading {
  color: #777; /* Cor do sub-título */
}

.service-heading {
  color:#d7a449; /* Cor dos títulos dos serviços */
  text-shadow: 3px 3px 0 hsl(0, 0%, 0%, 0.25);
}

.text-muted {
  color: #777; /* Cor do texto informativo */
}

.copyright,
.video-maker,
.social-media,
.marketing-digital {
  border-radius: 50%;
  max-width: 100%;
  height: auto;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.service-item:hover {
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* Adiciona uma sombra suave ao passar o mouse */
}

.row {
  margin-bottom: 30px; /* Adiciona espaço entre as linhas (rows) */
}

.service-item {
  padding: 20px; /* Adiciona espaçamento interno para os itens de serviço */
}

.service-heading {
  margin-top: 10px; /* Adiciona espaço acima dos títulos dos serviços */
}

.text-muted {
  margin-bottom: 20px; /* Adiciona espaço abaixo do texto informativo */
}
</style>
