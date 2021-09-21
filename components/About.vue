<template>
  <span class="flex flex-col justify-center">
    <div class="playfair mc-title">
      <p>About</p>
    </div>
    <div class="mc-about-content" v-html="abouttexts">
      {{ abouttexts }}
    </div>
  </span>
</template>

<script>
export default {
  props: ['abouttexts']
}
</script>

<style>
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
