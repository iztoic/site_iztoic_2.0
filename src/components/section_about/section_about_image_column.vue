<template>
    <div class="image-column">
        <div class="inner-column " data-wow-delay="0ms" data-wow-duration="1500ms">
            <div class="image">
                <img :src="currentImage" alt="">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SubSectionContentImage',
    data() {
        return {
            images: [
                "src/assets/img/people_drone.jpg",
                "src/assets/img/wine_bar.jpg",
                "src/assets/img/drone_tecnology.jpg",
                "src/assets/img/restaurant_drink.jpg",
            ],
            currentImageIndex: 0,
        };
    },
    computed: {
        currentImage() {
            return this.images[this.currentImageIndex];
        },
    },
    mounted() {
        this.startImageRotation();
    },
    methods: {
        startImageRotation() {
            setInterval(() => {
                this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
            }, 5000);
        },
    },
};
</script>

<style scoped>
@import url('./src/assets/style/styles.css');

.image-column {
    position: relative;
    width: 35vw;
    margin-top: 70px;
}

.inner-column {
    position: relative;
    padding: 5% 5% 0% 0%;
    margin-left: 5%;

    &::after {
        position: absolute;
        content: '';
        right: 0px;
        top: 0px;
        left: 40px;
        bottom: 100px;
        z-index: -1;
        border: 2px solid #d7a449;
    }
}

.image {
    position: relative;
    overflow: hidden;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 100%;
    height: 100%;

    &::before {
        position: absolute;
        content: '';
        left: -50px;
        width: 40vh;
        height: 20%;
    }
}

img {
    position: relative;
    width: 100%;
    display: block;
    transition: opacity 1.5s ease-in-out, transform 1.5s ease-in-out;
    object-fit: cover;
    border-radius: 10px;
}

img.fade-enter,
img.fade-leave-to {
    opacity: 1;
    transform: scale(1.9);
}

img.fade-enter-active,
img.fade-leave-active {
    opacity: 0;
    transform: scale(1);
}

.overlay-box {
    position: absolute;
    left: 40px;
    bottom: 48px;
}

.year-box {
    position: relative;
    color: #252525;
    font-size: 24px;
    font-weight: 700;
    line-height: 1.4em;
    padding-left: 125px;
}

.number {
    position: absolute;
    left: 0px;
    top: 0px;
    width: 110px;
    height: 110px;
    color: #d7a449;
    font-size: 68px;
    font-weight: 700;
    line-height: 105px;
    text-align: center;
    background-color: #ffffff;
    border: 1px solid #000000;
}


@media (max-width: 767px) {


    .inner-column {
        padding-right: 0px;
    }
}

@media (max-width: 575px) {

}
</style>