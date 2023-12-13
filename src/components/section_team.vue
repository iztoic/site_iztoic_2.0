<template>
    <div>
      <section id="section-team" class="bg-light-gray">
        <div class="container">
          <div class="row">
            <div class="col-lg-12 text-center">
              <h2 class="section-heading">Our Amazing Team</h2>
              <h3 class="section-subheading text-muted">
                Lorem ipsum dolor sit amet consectetur.
              </h3>
            </div>
          </div>
          <div class="row">
            <div class="col-sm-4">
              <div class="team-member">
                <img
                  src="http://www.mycatspace.com/wp-content/uploads/2013/08/adopting-a-cat.jpg"
                  class="img-responsive img-circle"
                  alt=""
                />
                <h4>Kay Garland</h4>
                <p class="text-muted">Lead Designer</p>
                <div class="card card0">
                  <div class="border">
                    <h2>Al Pacino</h2>
                    <div class="icons">
                      <i class="fa fa-codepen" aria-hidden="true"></i>
                      <i class="fa fa-instagram" aria-hidden="true"></i>
                      <i class="fa fa-dribbble" aria-hidden="true"></i>
                      <i class="fa fa-twitter" aria-hidden="true"></i>
                      <i class="fa fa-facebook" aria-hidden="true"></i>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-sm-4">
              <div class="team-member">
                <img
                  src="http://www.mycatspace.com/wp-content/uploads/2013/08/adopting-a-cat.jpg"
                  class="img-responsive img-circle"
                  alt=""
                />
                <h4>Larry Parker</h4>
                <p class="text-muted">Lead Marketer</p>
                <div class="card card1">
                  <div class="border">
                    <h2>Ben Stiller</h2>
                    <div class="icons">
                      <i class="fa fa-codepen" aria-hidden="true"></i>
                      <i class="fa fa-instagram" aria-hidden="true"></i>
                      <i class="fa fa-dribbble" aria-hidden="true"></i>
                      <i class="fa fa-twitter" aria-hidden="true"></i>
                      <i class="fa fa-facebook" aria-hidden="true"></i>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-sm-4">
              <div class="team-member">
                <img
                  src="http://www.mycatspace.com/wp-content/uploads/2013/08/adopting-a-cat.jpg"
                  class="img-responsive img-circle"
                  alt=""
                />
                <h4>Diana Pertersen</h4>
                <p class="text-muted">Lead Developer</p>
                <div class="card card2">
                  <div class="border">
                    <h2>Patrick Stewart</h2>
                    <div class="icons">
                      <i class="fa fa-codepen" aria-hidden="true"></i>
                      <i class="fa fa-instagram" aria-hidden="true"></i>
                      <i class="fa fa-dribbble" aria-hidden="true"></i>
                      <i class="fa fa-twitter" aria-hidden="true"></i>
                      <i class="fa fa-facebook" aria-hidden="true"></i>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-lg-8 col-lg-offset-2 text-center">
              <p class="large text-muted">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aut
                eaque, laboriosam veritatis, quos non quis ad perspiciatis, totam
                corporis ea, alias ut unde.
              </p>
            </div>
          </div>
        </div>
      </section>
    </div>
  </template>
  
  <script>
  export default {
    name: "SectionTeam",
    components: {
    }
  };
  </script>
  
  <style scoped>
  /* Container */
  .cardcontainer {
    height: 100vh;
    width: 100vw;
    max-height: 800px;
    max-width: 1280px;
    min-height: 600px;
    min-width: 1000px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: 0 auto;
  }
  
  /* Border */
  .border {
    height: 369px;
    width: 290px;
    background: transparent;
    border-radius: 10px;
    transition: border 1s;
    position: relative;
  }
  
  .border:hover {
    border: 1px solid white;
  }
  
  /* Card */
  .card {
    height: 379px;
    width: 300px;
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
  
  /* Card 0 */
  .card0 {
    background: url("https://i.pinimg.com/736x/8f/a0/51/8fa051251f5ac2d0b756027089fbffde--terry-o-neill-al-pacino.jpg")
      center center no-repeat;
    background-size: 300px;
  }
  
  .card0:hover {
    background: url("https://i.pinimg.com/736x/8f/a0/51/8fa051251f5ac2d0b756027089fbffde--terry-o-neill-al-pacino.jpg")
      left center no-repeat;
    background-size: 600px;
  }
  
  .card0:hover h2,
  .card0:hover .fa {
    opacity: 1;
  }
  
  /* Card 1 */
  .card1 {
    background: url("https://i.pinimg.com/originals/28/d2/e6/28d2e684e7859a0dd17fbd0cea00f8a9.jpg")
      center center no-repeat;
    background-size: 300px;
  }
  
  .card1:hover {
    background: url("https://i.pinimg.com/originals/28/d2/e6/28d2e684e7859a0dd17fbd0cea00f8a9.jpg")
      left center no-repeat;
    background-size: 600px;
  }
  
  .card1:hover h2,
  .card1:hover .fa {
    opacity: 1;
  }
  
  /* Card 2 */
  .card2 {
    background: url("https://i.pinimg.com/originals/ee/85/08/ee850842e68cfcf6e3943c048f45c6d1.jpg")
      center center no-repeat;
    background-size: 300px;
  }
  
  .card2:hover {
    background: url("https://i.pinimg.com/originals/ee/85/08/ee850842e68cfcf6e3943c048f45c6d1.jpg")
      left center no-repeat;
    background-size: 600px;
  }
  
  .card2:hover h2,
  .card2:hover .fa {
    opacity: 1;
  }
  
  /* Heading 2 */
  h2 {
    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
    color: white;
    margin: 20px;
    opacity: 0;
    transition: opacity 1s;
  }
  
  /* Font Awesome */
  .fa {
    opacity: 0;
    transition: opacity 1s;
  }
  
  /* Icons */
  .icons {
    position: absolute;
    fill: #fff;
    color: #fff;
    height: 130px;
    top: 226px;
    width: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
  }
  </style>
  