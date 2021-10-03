<template>
  <span class="parent flex flex-col">
    <span class="flex flex-col">
      <div class="top-heading playfair">
        <p>Hi. My name is</p>
      </div>
      <div class="main-heading">
        <p>PAU ABELLA</p>
      </div>
      <div class="sub-heading">
        <p v-if="$fetchState.pending">...</p>
        <p v-else-if="$fetchState.error">:(</p>
        <div v-else v-html="maintexts[0].subheading"> {{ maintexts[0].subheading }}</div>
      </div>
    </span>

    <div class="main-content">
      <About :abouttexts="maintexts[0].about" />
      <Projects />
      <Footer />
    </div>
  </span>
</template>

<script>
export default {
  data () {
    return {
      maintexts: []
    }
  },
  async fetch () {
    this.maintexts = await fetch(
      'https://pauabella-portfolio-api.herokuapp.com/main-texts'
    ).then(res => res.json())
  },
  head () {
    return {
      link: [
        {
          rel: 'stylesheet',
          href: 'https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&display=swap'
        }
      ]
    }
  }
}
</script>

<style>
@font-face {
  font-family: 'Helvetica';
  font-display: swap;
  src: url('~assets/fonts/Helvetica-Bold.ttf') format('truetype');
}
@font-face {
  font-family: 'Gobold';
  font-display: swap;
  src: url('~assets/fonts/Gobold High Bold.otf') format('truetype');
}

.body {
  background-color: #000202;
}

p {
  color: #fff;
  font-family: 'Helvetica', sans-serif;
}

.playfair, .playfair p {
  font-family: 'Playfair Display', serif !important;
}

.underline-gradient {
  border-style: solid;
  border-width: 0 0 .28vw 0;
  border-image: linear-gradient(90deg, #9D6A06, #910330, #5E0BBD, #00698E) 1;
  display: inline-block;
  line-height: 2vw;
}

.line-container {
  padding: 1.3vw 0 0 2.3vw;
}

a {
  -moz-transition: all .1s;
  -webkit-transition: all .1s;
  -o-transition: all .1s;
  transition: all .1s;
}
  a:hover {
    /* font-style: italic; */
    -webkit-transform: skewX(-20deg);
    -moz-transform: skewX(-20deg);
    -o-transform: skewX(-20deg);
    transform: skewX(-20deg);
  }

::selection, ::moz-selection {
  color: black;
  background-color: white;
}

.top-heading p {
  font-size: 7.6vw;
  line-height: 130%;
  padding-left: 3.2vw;
}
.main-heading p {
  font-family: 'Gobold', sans-serif;
  font-size: 36vw;
  text-align: center;
  line-height: 105%;

  background: -webkit-linear-gradient(0deg, #9D6A06, #910330, #5E0BBD, #00698E);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.main-heading p::selection, .main-heading p::moz-selection {
  -webkit-text-fill-color: black;
}
.sub-heading p {
  font-size: 1.82vw;
  padding-left: 3.2vw;
}

.main-content {
  margin-top: 8vw;
  padding: 0 15vw 0 15vw; /* <--"lateral bands" */
}
</style>
