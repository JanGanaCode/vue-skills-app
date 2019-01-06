<template>
  <div class="about">
    <h1>About</h1>
    <a href="https://www.jangana.com" target="_blank">
      <i class="fas fa-globe"></i>
      HomePage
    </a>
    <a href="https://github.com/JanGanaCode" target="_blank">
      <i class="fab fa-github"></i>
      GitHub
    </a>
    <a href="https://www.linkedin.com/in/jangana/" target="_blank">
      <i class="fab fa-linkedin"></i>
      LinkedIn
    </a>
    <a href="https://codepen.io/JanGana/" target="_blank">
      <i class="fab fa-codepen"></i>
      CodePen
    </a>
    <a href="https://www.instagram.com/janganacode/" target="_blank">
      <i class="fab fa-instagram"></i>
      Instagram
    </a>
    <p>v 1.0.0</p>
  </div>
</template>


<style scoped>
@import "https://use.fontawesome.com/releases/v5.6.3/css/all.css";

.about {
  margin-top: 60px;
}

.link {
  cursor: pointer;
}

i {
  color: #333;
  width: 45px;
}

a {
  display: block;
  text-decoration: none;
  color: #333;
  transition: 0.2s ease-in-out;
  padding: 5px 0;
}

a:hover i,
a:hover {
  color: grey;
}
</style>
