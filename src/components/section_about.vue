<template>
    <section id="section-about" class="section-about">
    <div class="container">
        <div class="row clearfix">
            
            <!--Content Column-->
            <div class="content-column col-md-6 col-sm-12 col-xs-12">
                <div class="inner-column">
                    <div class="sec-title">
                        <div class="title">Sobre Nós</div>
                        <h2>We Are The Leader In <br> The Interiores</h2>
                    </div>
                    <div class="text">Somos uma agência criativa que trabalha com sua maior paixão: O desenvolvimento de soluções estratégicas para conectar sua marca com o consumidor de forma humanizada. <br> Somos uma equipe que traz o design e o marketing de um jeito unico para dar forma a um único objetivo: Tornar sua marca ainda mais relevante para as pessoas, ajudando a construir seu sonho.</div>
                    </div>
            </div>
            
            <!--Image Column-->
            <div class="image-column col-md-6 col-sm-12 col-xs-12">
                <div class="inner-column " data-wow-delay="0ms" data-wow-duration="1500ms">
                    <div class="image">
                        <img src="src/assets/portifolio/people_drone.jpg" alt="">
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>
</template>

<script>
    export default {
    name: "SectionAbout",
        
    }
</script>

<style scoped>
.section-about{
position:relative;
padding:120px 0px;
}

.section-about .content-column{
position:relative;
margin-bottom:40px;
}

.section-about .content-column .inner-column{
position:relative;
padding-top:50px;
padding-right:100px;
}

.section-about .content-column .text{
position:relative;
color:#777777;
font-size:15px;
line-height:2em;
margin-bottom:40px;
}

.section-about .content-column .email{
position:relative;
color:#252525;
font-weight:700;
margin-bottom:50px;
}

.section-about .image-column{
position:relative;
margin-bottom:50px;
}

.section-about .image-column .inner-column{
position:relative;
padding:40px 40px 0px 0px;
margin-left:50px;
}

.section-about .image-column .inner-column:after{
position:absolute;
content:'';
right:0px;
top:0px;
left:40px;
bottom:100px;
z-index:-1;
border:2px solid #d7a449;
}

.section-about .image-column .inner-column .image{
position:relative;
}

.section-about .image-column .inner-column .image:before{
position:absolute;
content:'';
left:-50px;
bottom:-50px;
width:299px;
height:299px;
}

.section-about .image-column .inner-column .image img{
position:relative;
width:100%;
display:block;
}

.section-about .image-column .inner-column .image .overlay-box{
position:absolute;
left:40px;
bottom:48px;
}

.section-about .image-column .inner-column .image .overlay-box .year-box{
position:relative;
color:#252525;
font-size:24px;
font-weight:700;
line-height:1.4em;
padding-left:125px;
}

.section-about .image-column .inner-column .image .overlay-box .year-box .number{
position:absolute;
left:0px;
top:0px;
width:110px;
height:110px;
color:#d7a449;
font-size:68px;
font-weight:700;
line-height:105px;
text-align:center;
background-color:#ffffff;
border:1px solid #000000;
}
.section-about .btn-style-three:before {
position: absolute;
content: '';
left: 10px;
top: 10px;
z-index: -1;
right: -10px;
bottom: -10px;
background: url(https://i.ibb.co/DKn55Qz/pattern-1.jpg) repeat;
}
.section-about .btn-style-three:hover {
color: #ffffff;
background: #d7a449;
}
.section-about .btn-style-three {
position: relative;
line-height: 24px;
color: #252525;
font-size: 15px;
font-weight: 700;
background: none;
display: inline-block;
padding: 11px 40px;
background-color: #ffffff;
text-transform: capitalize;
border: 2px solid #d7a449;
font-family: 'Arimo', sans-serif;
}
.sec-title2{
color:#fff;
}
.sec-title {
position: relative;
padding-bottom: 40px;
}
.sec-title .title {
position: relative;
color: #d7a449;
font-size: 18px;
font-weight: 700;
padding-right: 50px;
margin-bottom: 15px;
display: inline-block;
text-transform: capitalize;
}
.sec-title .title:before {
position: absolute;
content: '';
right: 0px;
bottom: 7px;
width: 40px;
height: 1px;
background-color: #bbbbbb;
}

</style>