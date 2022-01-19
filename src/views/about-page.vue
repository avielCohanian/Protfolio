<template>
  <section class="about-page full">
    <a name="about"></a>

    <div class="container">
      <img src="../assets/img/Aviel.jpg" alt="" />
      <div>
        <h3>ABOUT ME</h3>

        <p>
          Hello, my name is Aviel Cohanian. I'm a Full Stack Web Developer, with experience in writing
          single-page-applications using the latest WEB technologies such as JavaScript (ES6, ES5), Vue.js, Angular,
          React and Node.js.
        </p>
        <p>
          Hard worker, passionate about solving challenges, focusing on problem solving and detailed orientation,
          self-learner, team player with strong communication skills.
        </p>
        <p>Check Out my latest projects - all code is available on my <a class="pointer" @click="open">Github</a>.</p>

        <div class="icon-container">
          <img src="../assets/img/svg/vue.svg" alt="" />
          <img src="../assets/img/svg/angular.svg" alt="" />
          <img src="../assets/img/svg/react.svg" alt="" />
          <img src="../assets/img/svg/node-js.svg" alt="" />
          <img src="../assets/img/svg/js.svg" alt="" />
          <img src="../assets/img/svg/sass.svg" alt="" />
          <img src="../assets/img/svg/css3.svg" alt="" />
          <img src="../assets/img/svg/html5.svg" alt="" />
          <img src="../assets/img/svg/github12.svg" alt="" />
        </div>
        <div class="resume">
          <a href="/resume/Resume.pdf" download="Aviel-resume.pdf">CV </a>
          <a @click="open">GH</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  export default {
    methods: {
      open() {
        window.open('https://github.com/avielCohanian');
      },
    },
  };
</script>

<style></style>
