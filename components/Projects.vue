<template>
  <span class="flex flex-col justify-center sep">
    <div class="playfair mc-title mb-7 flex flex-row items-center justify-between">
      <p>Projects</p>
      <span class="line-container">
        <svg width="100%" height="5" viewBox="0 0 1082 5" fill="none" xmlns="http://www.w3.org/2000/svg">
          <line
            x1="2.18557e-07"
            y1="2.5"
            x2="1082"
            y2="2.50009"
            stroke="url(#paint0_linear)"
            stroke-width="5"
          />
          <defs>
            <linearGradient
              id="paint0_linear"
              x1="-67.6979"
              y1="5.49999"
              x2="1173.92"
              y2="5.48816"
              gradientUnits="userSpaceOnUse"
            >
              <stop stop-color="#9D6A06" />
              <stop offset="0.333333" stop-color="#910330" />
              <stop offset="0.645833" stop-color="#5E0BBD" />
              <stop offset="1" stop-color="#00698E" />
            </linearGradient>
          </defs>
        </svg>
      </span>
    </div>
    <p v-if="$fetchState.pending">...</p>
    <p v-else-if="$fetchState.error">:(</p>
    <div v-else class="project-list">
      <div v-for="project of projects" :key="project.id">
        <no-ssr>
          <Project :project="project" />
        </no-ssr>
      </div>
    </div>
  </span>
</template>

<script>
export default {
  data () {
    return {
      projects: []
    }
  },
  async fetch () {
    this.projects = await fetch(
      'https://pauabella-portfolio-api.herokuapp.com/projects'
    ).then(res => res.json())
  }
}
</script>

<style>
.sep {
  margin-top: 9vw;
}

.mc-title {
  padding-left: 1vw;
  font-size: 5vw;
}

.mc-about-content p {
  text-align: justify;
  font-size: 1.5vw;
  line-height: 1.9vw;
  padding: .5vw 0 .5vw 0;
}
</style>
