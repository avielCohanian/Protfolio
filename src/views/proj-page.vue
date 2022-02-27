<template>
  <section class="proj-page" :class="{ 'dark-mode-proj': isDarkMode }">
    <ul class="clean-list" @keydown="checkSlide($event)">
      <div class="select-btn btn-filter">
        <a :class="isActive('vanilla')" @click="select('vanilla')"
          ><span class="none"> Vanilla</span> <i class="fab fa-js-square"></i>
          <img src="../assets/img/js.png" alt="" />
        </a>

        <a :class="isActive('vue')" class="vue" @click="select('vue')">
          <span class="none">Vue </span>
          <i class="fab fa-vuejs"></i>
          <img src="../assets/img/vue.png" alt="" />
        </a>
        <a :class="isActive('react')" @click="select('react')">
          <span class="none">React </span>
          <i class="fab fa-react"></i>
          <img src="../assets/img/react.png" alt="" />
        </a>
        <!-- <a :class="isActive('angular')" @click="select('angular')"
          ><span class="none">Angular </span><i class="fab fa-angular"></i>
          <img src="../assets/img/angular.png" alt="" />
        </a> -->
      </div>
      <li v-if="projectsToDisplay && projectsToDisplay.length">
        <proj-preview v-for="(proj, idx) in projectsToDisplay" :key="idx + proj.title" :idx="idx" :page="page">
          <article>
            <h2>{{ proj.title }}</h2>
            <p>{{ proj.description }}</p>
            <p v-if="proj.mainTechnology"><b>Main Technology:</b> {{ proj.mainTechnology }}</p>
            <p v-if="proj.stateManagement"><b>State Management:</b> {{ proj.stateManagement }}</p>
            <p v-if="proj.serverSide"><b>Server Side:</b> {{ proj.serverSide }}</p>
            <p v-if="proj.database"><b>Database:</b> {{ proj.database }}</p>
            <p v-if="proj.style"><b>Style:</b> {{ proj.style }}</p>
            <p v-if="proj.libraries"><b>Libraries:</b> {{ proj.libraries }}</p>
            <p v-if="proj.otherTechnologies"><b>Other Technologies:</b> {{ proj.otherTechnologies }}</p>
            <div class="btn-container">
              <a class="view-btn pointer" v-if="proj.projLink" @click="open(proj.projLink)">
                <a> View It Here</a> <span class="hidden"></span>
              </a>
              <a class="view-btn pointer" v-if="proj.code" @click="open(proj.code)">
                <a>View Github Repo</a> <span class="hidden"></span>
              </a>
            </div>
          </article>
          <img :src="proj.img" alt="" />
        </proj-preview>
        <template v-if="projectsToDisplay.length > 1">
          <i @click="prev" class="fas fa-chevron-left btn"></i>
          <i @click="next" class="fas fa-chevron-right btn"></i>
        </template>
      </li>
      <div class="proj-idx">
        <span
          v-for="n in projectsToDisplay.length"
          :key="n"
          :style="{ 'background-color': n - 1 === page ? '#ff00005c' : '#9e9e9e6b' }"
          @click="page = n - 1"
          :title="projectsToDisplay[n - 1].title"
        ></span>
      </div>
    </ul>
  </section>
</template>

<script>
  import ProjPreview from '../cmp/proj-preview.vue';
  export default {
    name: 'proj-page',
    props: ['isDarkMode'],
    data() {
      return {
        projects: [
          {
            title: 'Trelix',
            description:
              'Trello-based task management system. The system uses the Kanban-style method and is suitable for personal, group and organizational task management. Allows a variety of options for the user.',
            mainTechnology: 'Vue.js (with Vue CLI)',
            stateManagement: 'Vuex',
            serverSide: 'Node.js',
            database: 'Mongodb (on Atlas cloud)',
            style: 'SCSS',
            libraries:
              'Axios (http requests), Socket.io (Web Sockets), Vue-smooth-dnd (Drag and Drop), Vue router, Font Awesome (Icons)',
            otherTechnologies: 'Session Storage',
            img: require('../assets/img/trelix.png'),
            projLink: 'https://trelix--4.herokuapp.com/#/',
            code: 'https://github.com/avielCohanian/Trelix',
          },
          {
            title: 'Spotifo(In progress)',
            description: 'Play songs and select preferences by artists / songs.',
            mainTechnology: 'React',
            stateManagement: 'Redux',
            serverSide: 'Node.js',
            database: 'Mongodb (on Atlas cloud)',
            style: 'SCSS',
            libraries: 'Axios (http requests), Socket.io (Web Sockets), React router, Font Awesome (Icons)',
            otherTechnologies: 'Session Storage',
            img: require('../assets/img/spoty.png'),
            projLink: 'https://spotify15.herokuapp.com/#/',
            code: 'https://github.com/avielCohanian/spotifo',
          },
          {
            title: 'Mister Keep',
            description:
              'Google-Keep-Based application, that allows users to make different kinds of notes, including text, lists, images, video and audio (via Youtube link), and also map locations. The notes are saved automatically in the Local Storage.',
            mainTechnology: ' Vue.js',
            style: 'Vue router, Font Awesome (Icons)',
            otherTechnologies: 'Local Storage',
            img: require('../assets/img/appsus.png'),
            projLink: 'https://appsus.netlify.app/#/keep',
            code: 'https://github.com/avielCohanian/-Appsus',
          },
          {
            title: 'Meme Generator',
            description:
              'With Meme Generator you can create the funniest memes and share them with your friends on Facebook, Download to your computer, or save on the website (via Local Storage). You can use in our photo gallery, or upload your own image. Other features include adding text, stickers, choosing fonts and colors.',
            mainTechnology: 'Vanilla JavaScript',
            mainTechnology: 'Vanilla JavaScript',
            style: 'CSS3',
            otherTechnologies: 'Canvas, Local Storage',
            img: require('../assets/img/memeGenerator.png'),
            projLink: 'https://avielcohanian.github.io/Meme-Generator/',
            code: 'https://github.com/avielCohanian/Meme-Generator',
          },
          {
            title: 'Minesweeper',
            description:
              'The classic Minesweeper board game in a new version with new features (hints, safe-clicks, lives and "undo" option).',
            mainTechnology: 'Vanilla JavaScript',
            style: 'CSS3',
            otherTechnologies: 'Local Storage',
            img: require('../assets/img/MineSweeper.png'),
            projLink: 'https://avielcohanian.github.io/MineSweeper/',
            code: 'https://github.com/avielCohanian/MineSweeper',
          },
          {
            title: 'Mister-BITcoin(Free work)',
            description: ' A digital wallet for holding my bitcoins and sending (paying) them to my contact.',
            mainTechnology: 'React',
            stateManagement: 'Redux',
            serverSide: 'Firebase',
            database: 'Firebase',
            style: 'SCSS',
            libraries: 'Axios (http requests),Redux, Firebase,Chart.js, Material-ui',
            otherTechnologies: 'Firebase authentication',
            img: require('../assets/img/mister-bitcoin.png'),
            projLink: 'https://avielcohanian.github.io/Mister-BITcoin-React/',
            code: 'https://github.com/avielCohanian/Mister-BITcoin-React',
          },
        ],
        page: 0,
        filter: '',
        slideDirection: '',
      };
    },
    methods: {
      open(url) {
        window.open(url);
      },
      next() {
        this.page++;
        if (this.page >= this.projsLength) {
          this.page = 0;
        }
        this.slideDirection = 'slide-right';
      },
      prev() {
        this.page--;
        if (this.page < 0) {
          this.page = this.projsLength - 1;
        }
        this.slideDirection = 'slide-left';
      },
      checkSlide(event) {
        if (event.keyCode === 39) {
          this.next();
        } else if (event.keyCode === 37) {
          this.prev();
        } else {
          return;
        }
      },
      select(filter) {
        this.filter = this.filter === filter ? '' : filter;
        this.page = 0;
      },
      isActive(type) {
        if (this.filter !== type) return 'simple-button';
        else return 'active';
      },
    },
    computed: {
      projsLength() {
        return this.projectsToDisplay.length;
      },
      projectsToDisplay() {
        let projsToDisplay = this.projects.slice();
        if (!this.filter) return projsToDisplay;
        else {
          projsToDisplay = projsToDisplay.filter((p) =>
            p.mainTechnology.toLowerCase().includes(this.filter.toLowerCase())
          );
        }
        return projsToDisplay;
      },
    },
    components: { ProjPreview },
  };
</script>

<style></style>
