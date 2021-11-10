<template>
  <header id="header">
      <div class="flex">
        <img src="@/assets/no-avatar.png" alt="Avatar">
        <h1 v-if="!smallScreen()">Ethan Sachse</h1>
        <h1 v-if="smallScreen()">ES</h1>
      </div>
      <div class="flex">
        <!-- <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link> -->
      </div>
      <div id="nav-right" class="flex">
        <a href="https://www.github.com/esoxy8/" target="_blank"><i class="bi bi-github icons"></i></a>
        <a href="https://www.linkedin.com/in/ethansachse/" target="_blank"><i class="bi bi-linkedin icons"></i></a>
        <a href="./resume.pdf" target="_blank"><i class="bi bi-file-earmark-person-fill icons"></i></a>
      </div>
  </header>
  <router-view/>
  <footer id="footer">
    <div>
      <p>Powered by Vue</p>
    </div>
  </footer>
</template>

<script>
export default {
    name: 'App',
    methods: {
        smallScreen() {
            if (screen.width < 600) { return true; } else { return false; }
        }
    }
}
</script>

<style lang="scss">
@import "@/styles/main.scss";
* {
  margin: 0;
  padding: 0;
}

body {
  background: $black;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  background: $black;
}

#header {
  position: fixed;
  top: 0;
  width: 100%;
  height: 112px;
  z-index: 1;
  background: $black;
  border-bottom: 1px solid $turquoise;
}

.flex {
  display: flex;
  align-items: flex-start;
  justify-content: flex-start;

  h1 {
    font-size: 40px;
    margin-top: 32px;
    margin-left: 16px;
    font-weight: 100;
    color: $snow;
  }

  img {
    width: 64px;
    height: 64px;
    border-radius: 50%;
    margin-top: 24px;
    margin-left: 24px;
    margin-bottom: 24px;
    border: 3px solid $snow;
  }
}

#nav-right {
  position: absolute;
  top: 0;
  right: 0;

  a {
    font-size: 40px;
    color: $turquoise;
    padding: 24px 16px;
  }
}

#footer {
  position: fixed;
  left: 0;
  bottom: 0;
  height: 40px;
  width: 100%;
  background-color: $black;
  color: $turquoise;
  text-align: center;
  border-top: 1px solid $turquoise;

  p {
    font-size: 12px;
    padding: 8px;
  };
}
</style>