<template>
  <div class="home">
    <AboutMe />
    <Repos />
  </div>
</template>

<script lang="ts">
  import { Options, Vue } from 'vue-class-component';
  import AboutMe from '@/components/AboutMe.vue';
  import Repos from '@/components/Repos.vue';

  @Options({
    components: {
      AboutMe,
      Repos
    },
  })

  export default class Home extends Vue {}
</script>

<style scoped lang="scss">
@import "@/styles/main.scss";
  .home {
    margin-top: 112px;
    margin-bottom: 40px;
  }
</style>