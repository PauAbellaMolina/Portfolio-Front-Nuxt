<template>
  <span class="flex flex-col justify-center sep">
    <div class="playfair mc-title mb-7">
      <p>Projects</p>
    </div>
    <p v-if="$fetchState.pending">...</p>
    <p v-else-if="$fetchState.error">:(</p>
    <div v-else class="project-list">
      <div v-for="project of projects" :key="project.id">
        <Project :project="project" />
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
      'http://localhost:3030/projects'
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
