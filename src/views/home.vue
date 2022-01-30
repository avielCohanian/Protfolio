<template>
  <section class="main-layout home">
    <a name="home"></a>
    <app-header :userHasScrolled="userHasScrolled" />
    <home-page />
    <about-page />
    <a class="see-more" name="seeMore"></a>
    <proj-page />
    <contact />
    <a name="contact"></a>
    <a v-if="userHasScrolled" href="#home" class="up-button"> <i class="fas fa-arrow-up"></i></a>
    <!-- <span class="mouse-over" :style="{ left: pos.x + 'px', top: pos.y + 'px' }"></span> -->
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
      };
    },
    created() {
      addEventListener('scroll', () => {
        if (!window.scrollY) this.userHasScrolled = false;
        else this.userHasScrolled = true;
      });
      addEventListener('mousemove', (e) => {
        this.pos.x = e.pageX;
        this.pos.y = e.pageY;
      });
    },
    components: { AppHeader, HomePage, ProjPage, AboutPage, Contact },
  };
</script>
