<template>
  <header class="app-header" :class="{ scroll: userHasScrolled, 'dark-mode-header': isDarkMode }">
    <a class="logo" href="#home"><img src="../assets/img/A.png" alt="" /></a>
    <img class="icon" src="../assets/img/svg/bar.svg" alt="" />
    <div class="links">
      <a href="#home">HOME</a>
      <a href="#about">ABOUT</a>
      <a href="#seeMore">PROJECTS</a>
      <a href="#contact">CONTACT</a>
      <a class="mode" v-if="!isDarkMode" @click="changeMode">🌙</a>
      <a class="mode" v-else @click="changeMode">🌞</a>
    </div>
  </header>
</template>

<script>
  export default {
    name: 'app-header',
    props: ['userHasScrolled', 'isDarkMode'],
    methods: {
      changeMode() {
        this.$emit('changeMode');
      },
    },
  };
</script>

<style></style>
