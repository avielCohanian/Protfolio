<template>
  <section class="home-page" :class="{ 'dark-mode-home': isDarkMode }">
    <div>
      <h1>Aviel Cohanian</h1>
      <h3>Full Stack Web Developer</h3>
      <a href="#seeMore" class="see-more">See More <span></span> </a>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'home-page',
    props: ['isDarkMode'],
  };
</script>

<style></style>
