<template>
  <div class="parent-box flex flex-row">
    <div class="image" />
    <div class="project-info flex flex-col">
      <div class="pi-main">
        <p class="pi-main-title playfair">
          {{ project.title }}
        </p>
        <p class="pi-main-text" v-html="project.description_1">
          {{ project.description_1 }}
        </p>
        <p class="pi-main-text" v-html="project.description_2">
          {{ project.description_2 }}
        </p>
        <p class="pi-main-text" v-html="project.description_3">
          {{ project.description_3 }}
        </p>
        <p class="pi-main-text" v-html="project.description_4">
          {{ project.description_4 }}
        </p>
        <p class="pi-main-text" v-html="project.description_5">
          {{ project.description_5 }}
        </p>
      </div>
      <div class="pi-additional flex flex-row ml-2">
        <div class="pi-additional-left">
          <p class="pi-additional-title playfair">
            Developed with
          </p>
          <p class="pi-additional-text">
            {{ project.developed_1 }}
          </p>
          <p class="pi-additional-text">
            {{ project.developed_2 }}
          </p>
          <p class="pi-additional-text">
            {{ project.developed_3 }}
          </p>
          <p class="pi-additional-text">
            {{ project.developed_4 }}
          </p>
          <p class="pi-additional-text">
            {{ project.developed_5 }}
          </p>
          <p class="pi-additional-text">
            {{ project.developed_6 }}
          </p>
          <p class="pi-additional-text">
            {{ project.developed_7 }}
          </p>
          <p class="pi-additional-text">
            {{ project.developed_8 }}
          </p>
        </div>
        <div class="pi-additional-right">
          <p class="pi-additional-title playfair">
            Deployed on
          </p>
          <p class="pi-additional-text">
            {{ project.deployed_1 }}
          </p>
          <p class="pi-additional-text">
            {{ project.deployed_2 }}
          </p>
          <p class="pi-additional-text">
            {{ project.deployed_3 }}
          </p>
          <p class="pi-additional-text">
            {{ project.deployed_4 }}
          </p>
          <p class="pi-additional-text">
            {{ project.deployed_5 }}
          </p>
          <p class="pi-additional-text">
            {{ project.deployed_6 }}
          </p>
          <p class="pi-additional-text">
            {{ project.deployed_7 }}
          </p>
          <p class="pi-additional-text">
            {{ project.deployed_8 }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['project']
}
</script>

<style>
.parent-box {
  margin: 0 0 2em 1vw;
  height: 30vw;
  border-radius: 1.5vw;
  background-color: #0B0B0B;
}
  .image {
    background-color: #1B1B1B;
    border-radius: inherit;
    width: 50%;
  }
  .project-info {
    width: 50%;
    padding: 2vw 5vw 2vw 5vw;
    display: flex;
    align-items: center;
  }
    .pi-main {

    }
      .pi-main-title {
        font-size: 4vw;
      }
      .pi-main-text {
        margin: 0 0 1vw 0;
        font-size: 1.1vw;
        margin-left: 1.3vw;
        line-height: 115%;
      }
    .pi-additional {
      width: 100%;
    }
    .pi-additional-left, .pi-additional-right {
      width: 50%;
    }
      .pi-additional-title {
        font-size: 1.5vw;
      }
      .pi-additional-text {
        margin: 0 0 .1vw 0;
        font-size: .9vw;
        margin-left: 1vw;
        line-height: 115%;
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
