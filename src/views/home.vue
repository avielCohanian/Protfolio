<template>
  <section class="main-layout home" :class="{ 'dark-mode': isDarkMode }" ref="home">
    <a name="home"></a>
    <app-header :isDarkMode="isDarkMode" @changeMode="changeMode" :userHasScrolled="userHasScrolled" />
    <home-page :isDarkMode="isDarkMode" />

    <a class="about" name="about"></a>
    <about-page :isDarkMode="isDarkMode" />

    <a class="see-more" name="seeMore"></a>
    <proj-page :isDarkMode="isDarkMode" />

    <contact :isDarkMode="isDarkMode" />
    <a name="contact"></a>

    <a v-if="userHasScrolled" href="#home" class="up-button"> <i class="fas fa-arrow-up"></i></a>

    <span class="mouse-over full" :style="{ left: pos.x + 'px', top: pos.y + 'px' }"></span>
  </section>
</template>

<script>
  import AppHeader from '../cmp/app-header.vue';
  import Contact from '../cmp/contact.vue';
  import AboutPage from './about-page.vue';
  import HomePage from './home-page.vue';
  import ProjPage from './proj-page.vue';
  export default {
    name: 'home',
    data() {
      return {
        userHasScrolled: false,
        pos: { x: 0, y: 0 },
        isDarkMode: false,
      };
    },
    created() {
      addEventListener('scroll', () => {
        if (!window.scrollY) this.userHasScrolled = false;
        else this.userHasScrolled = true;
      });
    },
    methods: {
      changeMode() {
        this.isDarkMode = !this.isDarkMode;
      },
    },
    mounted() {
      if (window.screen.width < 500) return;
      this.$refs.home.addEventListener('mousemove', (e) => {
        this.pos.x = e.pageX;
        this.pos.y = e.pageY;
      });
    },
    destroyed() {
      this.$refs.home.removeEventListener('mousemove');
    },
    components: { AppHeader, HomePage, ProjPage, AboutPage, Contact },
  };
</script>
