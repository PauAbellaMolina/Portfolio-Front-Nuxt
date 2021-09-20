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
        <!-- <p>I am a Junior Software Developer highly passionate about engineering and design.</p>
        <p>Making cool things fast and pretty is the goal.</p> -->
        <p v-if="$fetchState.pending">...</p>
        <p v-else-if="$fetchState.error">:(</p>
        <div v-else v-html="maintexts[0].subheading"> {{ maintexts[0].subheading }}</div>
      </div>
    </span>

    <div class="main-content">
      <About :abouttexts="maintexts[0].about" />
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
      'http://localhost:3030/main-texts'
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
}
.sub-heading p {
  font-size: 1.82vw;
  padding-left: 3.2vw;
}

.main-content {
  margin-top: 8vw;
  padding: 0 10vw 0 10vw;
}
</style>
