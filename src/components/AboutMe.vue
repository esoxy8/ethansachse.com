<template>
  <div class="container">
    <div class="content">
      <h2>About Me</h2>
      <p>
        Hi, my name is Ethan and I am a software developer from Buffalo, NY. I have a BS degree
        in Computer Science from the University at Buffalo and 4 years of industry experience primarily 
        building web APIs in Go and single page front end applications in Vuejs and Angular. Additionally,
        I have experience deploying applications using Docker, Kubernetes, and CI/CD pipelines. I am also
        fascinated with blockchain technology, and spend lots of my free time researching the field in both
        core blockchain development and decentralized app development. My other hobbies include golfing, 
        playing ice hockey, and starting new side projects before I get anywhere close to finishing the one 
        I am currenly working on. Go Bills!
      </p>
    </div>
  </div>
</template>

<script lang="ts">
  import { Vue } from 'vue-class-component';
  export default class AboutMe extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import "@/styles/main.scss";

  .container {
    padding: 32px;
  }

  .content {
    max-width: 800px;
    padding: 24px;
    margin: auto;
    border-left: 3px solid $turquoise;
    background: $deepGray;
    border-radius: 10px;

    h2 {
      color: $snow;
    }

    p {
      color: $lavendar;
      font-size: 18px;
    }
  }
</style>
