<template>
	<div>
	  <div class="container">
		<div
        class="panel"
        v-bind:class="{ active: activePanel === 1 }"
        @click="setActivePanel(1)"
      >
        <video
		ref="video1"
          src="src/assets/video/video1.mov"
          autoplay
          :muted="activePanel !== 1"
          loop
          style="width: 100%; height: 100%; object-fit: cover;"
        ></video>
        <h3>MacBook</h3>
      </div>
  
		<div
		  class="panel"
		  v-bind:class="{ active: activePanel === 2 }"
		  @click="setActivePanel(2)"
		>
		<video
		ref="video2"
          src="src/assets/video/video2.mov"
          autoplay
          :muted="activePanel !== 1"
          loop
          style="width: 100%; height: 100%; object-fit: cover;"
        ></video>
		  <h3>Serenity</h3>
		</div>
		<div
		  class="panel"
		  v-bind:class="{ active: activePanel === 3 }"
		  @click="setActivePanel(3)"
		>
		<video
		ref="video3"
          src="src/assets/video/video3.mov"
          autoplay
          :muted="activePanel !== 1"
          loop
          style="width: 100%; height: 100%; object-fit: cover;"
        ></video>
		  <h3>Keyboard</h3>
		</div>
  
		<div
		  class="panel"
		  v-bind:class="{ active: activePanel === 4 }"
		  @click="setActivePanel(4)"
		>
		<video
		ref="video4"
          src="src/assets/video/video4.mov"
          autoplay
          :muted="activePanel !== 1"
          loop
          style="width: 100%; height: 100%; object-fit: cover;"
        ></video>
		  <h3>CodingMate</h3>
		</div>
  
		<div
		  class="panel"
		  v-bind:class="{ active: activePanel === 5 }"
		  @click="setActivePanel(5)"
		>
		<video
		ref="video5"
          src="src/assets/video/video5.mov"
          autoplay
          :muted="activePanel !== 1"
          loop
          style="width: 100%; height: 100%; object-fit: cover;"
        ></video>
		  <h3>Headphone</h3>
		</div>
	  </div>
	</div>
  </template>
  
  <script>
export default {
  name: "PortifolioGallery",
  data() {
    return {
      activePanel: null,
      videos: []
    };
  },
  methods: {
    setActivePanel(panelNumber) {
      if (this.activePanel !== null) {
        this.videos[this.activePanel - 1].muted = true;
      }
      this.activePanel = panelNumber;
      this.videos[panelNumber - 1].muted = false;
    },
	
	muteVideos() {
      const videos = document.querySelectorAll('video');
      videos.forEach(video => {
        if (!video.paused) {
          video.pause();
        }
      });
	}

  },
  mounted() {
    this.videos = [
      this.$refs.video1,
      this.$refs.video2,
      this.$refs.video3,
      this.$refs.video4,
      this.$refs.video5
    ];
	const plansClose = document.querySelector(".page_plans-close");
  plansClose.addEventListener("click", () => {
    // Mutar os vídeos
    this.muteVideos();

    // Definir o activePanel como 0 para fechar todos os cards
    this.activePanel = null;
  });
  // Adiciona eventos de clique a todos os vídeos
  this.videos.forEach((video, index) => {
      video.addEventListener('click', () => {
        if (video.paused) {
          this.muteVideos(); // Pausa todos os outros vídeos
          video.play();
        } else {
          video.pause();
        }
      });
    });
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Yantramanav&display=swap");

@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");

* {
	box-sizing: border-box;
}

body {
	background-color: rgb(36, 30, 44);
	font-family: -apple-system, BlinkMacSystemFont, "SF Pro Display", "Segoe UI",
		Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
	display: flex;
	align-items: center;
	justify-content: center;
	height: 100vh;
	overflow: hidden;
	margin: 0;
}

.container {
	display: flex;
	width: 80vw;
	height: 70vh;
}

.panel {
	box-shadow: 0px 16px 40px 2px rgba(1, 1, 0, 0.15);

	background-size: auto 100%;
	background-position: center;
	background-repeat: none;
	height: 80vh;
	border-radius: 8px;
	color: #fff;
	cursor: pointer;
	flex: 0.7;
	margin: 12px;
	position: relative;
	transition: flex 0.4s ease-in;
}

.panel h3 {
	font-size: 24px;
	letter-spacing: 2px;
	position: absolute;
	bottom: 24px;
	left: 24px;
	margin: 0;
	opacity: 0;
	color: rgb(0, 124, 207);
}

.panel.active {
	flex: 7;
}
.panel.active h3 {
	opacity: 1;
}

@media (max-width: 480px) {
	.container {
		width: 100vw;
	}
	.panel:nth-of-type(4),
	.panel:nth-of-type(5) {
		display: none;
	}
}

</style>
