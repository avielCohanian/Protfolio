<template>
  <section class="main-layout home">
    <a name="home"></a>
    <app-header :userHasScrolled="userHasScrolled" />
    <home-page />
    <about-page />
    <proj-page />
    <contact />
    <a name="contact"></a>
    <a v-if="userHasScrolled" href="#home" class="up-button"> </a>
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
      };
    },
    created() {
      addEventListener('scroll', () => {
        if (!window.scrollY) this.userHasScrolled = false;
        else this.userHasScrolled = true;
      });
    },
    components: { AppHeader, HomePage, ProjPage, AboutPage, Contact },
  };
</script>
