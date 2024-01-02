<template>
  <section id="section-books">
    <h1 class="pen-title">Ebooks</h1>
    <section id="main">
      <ul class="list-inline">
        <li v-for="(book, index) in books" :key="index" class="book">
          <img :src="book.image" />
        </li>
      </ul>
    </section>
  </section>
</template>

<script>
export default {
  name: "SectionBooks",
  data() {
    return {
      books: [
        {
          image: "https://d.gr-assets.com/books/1348927776l/8032112.jpg",
        },
        {
          image: "http://ecx.images-amazon.com/images/I/51oXKWrcYYL.jpg",
        },
        {
          image: "https://d.gr-assets.com/books/1348927776l/8032112.jpg",
        },
        {
          image: "http://ecx.images-amazon.com/images/I/51oXKWrcYYL.jpg",
        },
        {
          image: "http://ecx.images-amazon.com/images/I/51oXKWrcYYL.jpg",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
/* Variáveis */
:root {
  --color-bg: #fde3a7;
  --book-color-bg: lighten(var(--color-bg), 20%);
  --book-color-border: lighten(#000, 85%);
  --book-border: 1px solid var(--book-color-border);
}

#section-books{
  padding-bottom: 20px;
}

h1, h2, h3, h4, h5, h6 {
  font-family: var(--ff-display);
  line-height: 120%;
}
h1.pen-title {
  font-size: 3rem;
  margin: 0 0 1rem 0;
  text-align: center;
  text-shadow: 3px 3px 0 hsl(0, 0%, 0%, 0.25);
}

/* TECHNIQUE STYLES START HERE
-------------------------------------------------------- */
#main {
  align-items: center;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
  width: fit-content;
}

.pen-title{
  color:#d7a449;
}


/* Mixin */
.book-rounded-corners {
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;
}

/* Estilos */
body, html {
  width: 100%;
  height: 100%;
  display: table;
  text-align: center;
}

body {
  background: var(--color-bg);
}

ul {
  display: table-cell;
  vertical-align: middle;
}

.list-inline {
  padding-left: 0;
  list-style: none;
}

.list-inline > li {
  display: inline-block;
  margin-left: 2em;
}

.list-inline > li:first-child {
  margin-left: 0;
}

.book {
  cursor: pointer;
  display: block;
  width: 150px;
  height: 220px;
  position: relative;
  background: var(--book-color-bg);
  z-index: 1;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, .1), 0 9px 20px 0 rgba(0, 0, 0, .25);
  overflow: hidden;
  transition: box-shadow .3s linear;
}

.book img {
  width: inherit;
  height: inherit;
  transform-origin: 0 50%;
  transform: rotateY(0);
  transition: all .45s ease;
}

.book:hover {
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, .25), 0 9px 20px 0 rgba(0, 0, 0, .45);
}

.book:hover img {
  transform: rotateY(-25deg);
  box-shadow: 1px 1px 5px 5px rgba(0, 0, 0, .2);
}

.book::after,
.book::before {
  content: '';
  display: block;
  width: inherit;
  height: inherit;
  position: absolute;
  z-index: -1;
  top: 0;
  background: var(--book-color-bg);
  border: var(--book-border);
}

.book::before {
  left: -3px;
}

.book::after {
  left: -6px;
}
</style>