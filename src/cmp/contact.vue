<template>
  <div class="contact-me full">
    <h2>CONTACT ME</h2>
    <p><b>Tel:</b>050-3431443</p>
    <p><b>Mail:</b>avial151515@gmail.com</p>
    <div class="links">
      <img class="link showL" :src="linkedin" alt="" @click="open('https://www.linkedin.com/in/aviel-cohanian/')" />
      <!-- <img class="link hiddenL" :src="linkedin1" alt="" /> -->
      <img class="link" :src="git" alt="" @click="open('https://github.com/avielCohanian')" />
      <img class="link" :src="facebook" alt="" @click="open('https://www.facebook.com/aviel.cohanian')" />
      <i class="fab fa-github-square"></i>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        linkedin: require('../assets/img/linkedin.png'),
        linkedin1: require('../assets/img/linkedin1.png'),
        git: require('../assets/img/svg/github.svg'),
        facebook: require('../assets/img/svg/facebook.svg'),
      };
    },
    methods: {
      open(url) {
        window.open(url);
      },
    },
  };
</script>

<style></style>
