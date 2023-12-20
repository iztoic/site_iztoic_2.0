<template>
          <section id="section-testimonials">
            <figure class="snip1386">
  <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/sample18.jpg" alt="sample18" class="background" />
  <figcaption>
    <blockquote>Which is worse, that everyone has his price, or that the price is always so low.</blockquote>
    <h5>- Emily Barrow</h5>
  </figcaption><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/profile-sample1.jpg" alt="profile-sample1" class="profile" />
</figure>
<figure class="snip1386 hover"><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/sample10.jpg" alt="sample10" class="background" />
  <figcaption>
    <blockquote>I'm killing time while I wait for life to shower me with meaning and happiness.</blockquote>
    <h5>- Tim Forever</h5>
  </figcaption><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/profile-sample5.jpg" alt="profile-sample5" class="profile" />
</figure>
<figure class="snip1386"><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/sample19.jpg" alt="sample19" class="background" />
  <figcaption>
    <blockquote>The only skills I have the patience to learn are those that have no real application in life. </blockquote>
    <h5>- Jenny Jenkins</h5>
  </figcaption><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/profile-sample6.jpg" alt="profile-sample6" class="profile" />
</figure>
          </section>
</template>

<script>
export default {
    name: "SectionTestimonials"
};
</script>

<style scoped>
@import url(https://fonts.googleapis.com/css?family=Playfair+Display:400,900);

section{
    width: 100%;
    display: flex;
    justify-content: space-evenly;
}

blockquote{
    padding: 0;
    border-left:0px;
    
}
.snip1386 {
  font-family: 'Playfair Display', Arial, sans-serif;
  position: relative;
  overflow: hidden;
  margin: 10px;
  min-width: 230px;
  max-width: 315px;
  max-height: 220px;
  width: 100%;
  color: #000000;
  text-align: left;
  font-size: 16px;
  background-color: #000000;
}
.snip1386 * {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
.snip1386 .background {
  max-width: 100%;
  backface-visibility: hidden;
  opacity: 0.5;
}
.snip1386 figcaption {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  z-index: 1;
  opacity: 1;
  padding: 30px 10px 30px 0;
  background-color: #ffffff;
  width: 40%;
}
.snip1386 figcaption:before {
  position: absolute;
  top: 50%;
  -webkit-transform: translateY(-50%);
  transform: translateY(-50%);
  left: 100%;
  content: '';
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 120px 0 120px 120px;
  border-color: transparent transparent transparent #ffffff;
  margin-left: -1px;
}
.snip1386:after {
  position: absolute;
  bottom: 50%;
  left: 40%;
  content: '';
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 120px 120px 0 120px;
  border-color: rgba(255, 255, 255, 0.5) transparent transparent transparent;
}
.snip1386 h5,
.snip1386 blockquote {
  -webkit-transform: translateX(30px);
  transform: translateX(30px);
  margin: 0;
}
.snip1386 h5 {
  margin: 10px 0;
  line-height: 1.1em;
  font-weight: 900;
  color: #1a1a1a;
}
.snip1386 blockquote {
  font-size: 0.9em;
  font-style: italic;
}
.snip1386 .profile {
  position: absolute;
  width: 100px;
  border-radius: 50%;
  top: 50%;
  right: 25%;
  z-index: 1;
  -webkit-transform: translate(50%, -50%);
  transform: translate(50%, -50%);
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
}
.credibility{
  align-items: center;
  display: flex;
}

.snip1386:hover {
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.6);
  transform: scale(1.1);
  transition: box-shadow 0.6s ease, transform 0.6s ease;
}

.snip1386:hover figcaption {
  transition: padding 0.6s ease;
}

.snip1386 .background {
  transition: opacity 0.3s ease;
}

.snip1386:hover .background {
  opacity: 1;
}
.snip1386 .profile {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.snip1386:hover .profile {
  transform: translate(50%, -50%) scale(1.1);
  box-shadow: 0 0 30px rgba(0, 0, 0, 0.5);
}

</style>
