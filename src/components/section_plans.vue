<template>
    <section id="section-plans">
        <div>
        <div class="container">
        <div class="card" style="--clr1: #ff0080bf; --clr2: #ff00eabf; --text: #ff0080;">
            <div class="price">
                <h1>$0</h1>
                <p>/Month</p>
            </div>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="#fff" fill-opacity="1" d="M0,224L11.4,197.3C22.9,171,46,117,69,106.7C91.4,96,114,128,137,149.3C160,171,183,181,206,154.7C228.6,128,251,64,274,32C297.1,0,320,0,343,10.7C365.7,21,389,43,411,53.3C434.3,64,457,64,480,96C502.9,128,526,192,549,208C571.4,224,594,192,617,170.7C640,149,663,139,686,160C708.6,181,731,235,754,213.3C777.1,192,800,96,823,80C845.7,64,869,128,891,160C914.3,192,937,192,960,165.3C982.9,139,1006,85,1029,80C1051.4,75,1074,117,1097,149.3C1120,181,1143,203,1166,181.3C1188.6,160,1211,96,1234,69.3C1257.1,43,1280,53,1303,101.3C1325.7,149,1349,235,1371,224C1394.3,213,1417,107,1429,53.3L1440,0L1440,320L1428.6,320C1417.1,320,1394,320,1371,320C1348.6,320,1326,320,1303,320C1280,320,1257,320,1234,320C1211.4,320,1189,320,1166,320C1142.9,320,1120,320,1097,320C1074.3,320,1051,320,1029,320C1005.7,320,983,320,960,320C937.1,320,914,320,891,320C868.6,320,846,320,823,320C800,320,777,320,754,320C731.4,320,709,320,686,320C662.9,320,640,320,617,320C594.3,320,571,320,549,320C525.7,320,503,320,480,320C457.1,320,434,320,411,320C388.6,320,366,320,343,320C320,320,297,320,274,320C251.4,320,229,320,206,320C182.9,320,160,320,137,320C114.3,320,91,320,69,320C45.7,320,23,320,11,320L0,320Z"></path></svg>
            <div class="details">
                <h2>Primeiros passos PRO</h2>
                <div class="options">
                    <h4>Anuncio pago</h4>
                    <h4>Social media</h4>
                    <h4>Copyright</h4>
                    <h4>Filmaker</h4>
                </div>
            </div>
            <input type="submit" value="CHOOSE PLAN" v-on:click="choosePlan('Primeiros passos PRO')">
        </div>
        <div class="card" style="--clr1: #c04848bf; --clr2: #480048bf; --text: #c04848;">
            <div class="price">
                <h1>$99</h1>
                <h2>.00</h2>
                <p>/Month</p>
            </div>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="#fff" fill-opacity="1" d="M0,96L11.4,117.3C22.9,139,46,181,69,181.3C91.4,181,114,139,137,106.7C160,75,183,53,206,58.7C228.6,64,251,96,274,112C297.1,128,320,128,343,144C365.7,160,389,192,411,176C434.3,160,457,96,480,80C502.9,64,526,96,549,117.3C571.4,139,594,149,617,128C640,107,663,53,686,42.7C708.6,32,731,64,754,85.3C777.1,107,800,117,823,133.3C845.7,149,869,171,891,160C914.3,149,937,107,960,96C982.9,85,1006,107,1029,101.3C1051.4,96,1074,64,1097,69.3C1120,75,1143,117,1166,133.3C1188.6,149,1211,139,1234,133.3C1257.1,128,1280,128,1303,122.7C1325.7,117,1349,107,1371,122.7C1394.3,139,1417,181,1429,202.7L1440,224L1440,320L1428.6,320C1417.1,320,1394,320,1371,320C1348.6,320,1326,320,1303,320C1280,320,1257,320,1234,320C1211.4,320,1189,320,1166,320C1142.9,320,1120,320,1097,320C1074.3,320,1051,320,1029,320C1005.7,320,983,320,960,320C937.1,320,914,320,891,320C868.6,320,846,320,823,320C800,320,777,320,754,320C731.4,320,709,320,686,320C662.9,320,640,320,617,320C594.3,320,571,320,549,320C525.7,320,503,320,480,320C457.1,320,434,320,411,320C388.6,320,366,320,343,320C320,320,297,320,274,320C251.4,320,229,320,206,320C182.9,320,160,320,137,320C114.3,320,91,320,69,320C45.7,320,23,320,11,320L0,320Z"></path></svg>
            <div class="details">
                <h2>STANDARD</h2>
                <div class="options">
                    <h4>Anuncio pago</h4>
                    <h4>Social media</h4>
                    <h4>Copyright</h4>
                    <h4>Filmaker</h4>
                </div>
            </div>
            <input type="submit" value="CHOOSE PLAN" v-on:click="choosePlan('STANDARD')">
        </div>
        <div class="card" style="--clr1: #4cb8c4bf; --clr2: #3cd3adbf; --text: #4cb8c4;">
            <div class="price">
                <h1>$160</h1>
                <h2>.00</h2>
                <p>/Month</p>
            </div>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="#fff" fill-opacity="1" d="M0,32L11.4,53.3C22.9,75,46,117,69,144C91.4,171,114,181,137,181.3C160,181,183,171,206,181.3C228.6,192,251,224,274,234.7C297.1,245,320,235,343,229.3C365.7,224,389,224,411,213.3C434.3,203,457,181,480,149.3C502.9,117,526,75,549,58.7C571.4,43,594,53,617,96C640,139,663,213,686,208C708.6,203,731,117,754,117.3C777.1,117,800,203,823,208C845.7,213,869,139,891,96C914.3,53,937,43,960,37.3C982.9,32,1006,32,1029,64C1051.4,96,1074,160,1097,170.7C1120,181,1143,139,1166,117.3C1188.6,96,1211,96,1234,90.7C1257.1,85,1280,75,1303,106.7C1325.7,139,1349,213,1371,229.3C1394.3,245,1417,203,1429,181.3L1440,160L1440,320L1428.6,320C1417.1,320,1394,320,1371,320C1348.6,320,1326,320,1303,320C1280,320,1257,320,1234,320C1211.4,320,1189,320,1166,320C1142.9,320,1120,320,1097,320C1074.3,320,1051,320,1029,320C1005.7,320,983,320,960,320C937.1,320,914,320,891,320C868.6,320,846,320,823,320C800,320,777,320,754,320C731.4,320,709,320,686,320C662.9,320,640,320,617,320C594.3,320,571,320,549,320C525.7,320,503,320,480,320C457.1,320,434,320,411,320C388.6,320,366,320,343,320C320,320,297,320,274,320C251.4,320,229,320,206,320C182.9,320,160,320,137,320C114.3,320,91,320,69,320C45.7,320,23,320,11,320L0,320Z"></path></svg>
            <div class="details">
                <h2>PREMIUM</h2>
                <div class="options">
                    <h4>Anuncio pago</h4>
                    <h4>Social media</h4>
                    <h4>Copyright</h4>
                    <h4>Filmaker</h4>
                </div>
            </div>
            <input type="submit" value="CHOOSE PLAN" v-on:click="choosePlan('PREMIUM')">
        </div>
        <div class="card larger-card" style="--clr1: #6d6d6dbf; --clr2: #4a4a4abf; --text: #6d6d6d;">
        <div class="details">
          <h2>{{ selectedCard }}</h2>
          <ul>
            <li v-for="product in getProductList()" :key="product">{{ product }}</li>
          </ul>
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
      selectedCard: null,
    };
  },
  methods: {
    choosePlan(card) {
      this.selectedCard = card;
    },
    getProductList() {
      // Retorne uma lista de produtos com base na seleção
      switch (this.selectedCard) {
        case "Primeiros passos PRO":
          return ["Produto 1 PRO", "Produto 2 PRO", "Produto 3 PRO"];
        case "STANDARD":
          return ["Produto 1 STANDARD", "Produto 2 STANDARD", "Produto 3 STANDARD"];
        case "PREMIUM":
          return ["Produto 1 PREMIUM", "Produto 2 PREMIUM", "Produto 3 PREMIUM"];
        default:
          return [];
      }
    },
  },
};
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800&display=swap');


.container{
    min-height: 100%;
    display: flex;
    width: 100%;
    justify-content: center;
    align-items: center;
}

.card {
    height: 450px;
    width: 250px;
    position: relative;
    border-radius: 15px;
    overflow: hidden;
    background: #fff;
    margin: 0 5px;
    box-shadow: 0 0 20px rgba(0,0,0,0.4);
    transition: transform 0.4s;
}

.card:hover{
    transform: scale(1.2);
    z-index: 1000;
}

.card .price{
    height: 150px;
    width: 250px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.card:nth-child(1) .price{
    background: linear-gradient(to right, var(--clr1), var(--clr2)), url("https://images.unsplash.com/photo-1517732306149-e8f829eb588a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=872&q=80") center center/cover;
}
.card:nth-child(2) .price{
    background: linear-gradient(to right, var(--clr1), var(--clr2)), url("https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=871&q=80") center center/cover;
}
.card:nth-child(3) .price{
    background: linear-gradient(to right, var(--clr1), var(--clr2)), url("https://images.unsplash.com/photo-1501196354995-cbb51c65aaea?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=871&q=80") center center/cover;
}

.card .price h1{
    color: #fff;
    font-size: 40px;
    font-weight: 500;
}

.card .price h2{
    color: #fff;
    font-size: 20px;
    font-weight: 400;
    margin-top: -10px;
}

.card .price p{
    color: #fff;
    font-size: 15px;
    margin-bottom: -10px;
}

.card svg{
    position: absolute;
    top: 110px;
}

.card .details{
    height: 300px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.card .details h2{
    color: var(--text);
    font-weight: 600;
    font-size: 30px;
    margin-top: 20px;
    margin-bottom: 10px;
}

.card .details .options{
    text-align: center;
}

.card .details .options h4{
    font-size: 15px;
    font-weight: 500;
    margin-bottom: 5px;
}

.card input{
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
    width: 180px;
    height: 40px;
    border: none;
    border-radius: 20px;
    font-size: 16px;
    font-weight: 500;
    color: #fff;
    background: #bbb;
}


.card:hover input{
    background: linear-gradient(to right, var(--clr1), var(--clr2));
}

.card.larger-card {
    width: 400px; /* Ajuste o tamanho conforme necessário */
    height: 450px; /* Ajuste o tamanho conforme necessário */
  }

  .card input {
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
    width: 180px;
    height: 40px;
    border: none;
    border-radius: 20px;
    font-size: 16px;
    font-weight: 500;
    color: #fff;
    background: #bbb;
  }

  .card.larger-card .details ul {
    list-style-type: none;
    padding: 0;
  }

  .card.larger-card .details ul li {
    font-size: 18px;
    margin-bottom: 10px;
  }
</style>