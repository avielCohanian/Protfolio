<template>
  <div class="contact-me full" :class="{ 'dark-mode-contact': isDarkMode }">
    <h2>CONTACT ME</h2>
    <p><b>Tel:</b> 050-3431443</p>
    <p class="email-link" @click="open('https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=avielcohanian@gmail.com')">
      <b>Mail:</b> avielcohanian@gmail.com
    </p>
    <div class="links">
      <i class="fab fa-linkedin link" @click="open('https://www.linkedin.com/in/aviel-cohanian/')"></i>
      <i class="fab fa-github-square link" @click="open('https://github.com/avielCohanian')"></i>
      <i class="fab fa-facebook-square link" @click="open('https://www.facebook.com/aviel.cohanian')"></i>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['isDarkMode'],

    data() {
      return {};
    },
    methods: {
      open(url) {
        window.open(url);
      },
    },
  };
</script>

<style></style>
