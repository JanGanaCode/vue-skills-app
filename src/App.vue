<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>
    <router-view/>
  </div>
</template>

<script>
import Skills from "./components/Skills.vue";

export default {
  name: "app",
  components: {
    Skills
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Montserrat:400,700");

body {
  background-color: #eeeeee;
  font-family: "Montserrat", sans-serif;
  display: grid;
  grid-template-rows: auto;
  justify-items: center;
  padding-top: 50px;
}
body,
html {
  margin: 0;
  height: 100%;
}
#app {
  width: 50%;
}

nav {
  padding: 20px 20px 20px 0;
  position: fixed;
  top: 0;
}

nav a {
  padding: 10px;
  text-decoration: none;
  background: #35495e;
  border-radius: 3px;
  color: #42b883;
  font-weight: bold;
  margin-right: 15px;
}

@media (max-width: 767px) {
  #app {
    width: 90%;
  }
}
</style>
