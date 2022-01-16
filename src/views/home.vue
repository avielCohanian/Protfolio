<template>
  <section class="main-layout">
    <a name="home"></a>
    <app-header />
    <home-page />
    <about-page />
    <proj-page />
    <contact />
    <a name="contact"></a>
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
    components: { AppHeader, HomePage, ProjPage, AboutPage, Contact },
  };
</script>
