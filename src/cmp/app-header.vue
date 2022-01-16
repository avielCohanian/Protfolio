<template>
  <header class="app-header" :class="{ scroll: userHasScrolled }">
    <a class="logo" href="#home"><img src="../assets/img/A.png" alt="" /></a>
    <img class="icon" src="../assets/img/svg/bar.svg" alt="" />
    <div class="links">
      <a href="#home">HOME</a>
      <a href="#about">ABOUT</a>
      <a href="#seeMore">PROJECTS</a>
      <a href="#contact">CONTACT</a>
    </div>
  </header>
</template>

<script>
  export default {
    name: 'app-header',
    data() {
      return {
        userHasScrolled: false,
      };
    },
    created() {
      addEventListener('scroll', () => {
        if (!window.scrollY) this.userHasScrolled = false;
        else this.userHasScrolled = true;
      });
    },
  };
</script>

<style></style>
