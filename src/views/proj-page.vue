<template>
  <section class="proj-page">
    <a class="see-more" name="seeMore"></a>
    <ul class="clean-list">
      <li v-for="(proj, idx) in projects" :key="idx">
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
      </li>
    </ul>
  </section>
</template>

<script>
  export default {
    name: 'proj-page',
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
        ],
      };
    },
    methods: {
      open(url) {
        window.open(url);
      },
    },
  };
</script>

<style></style>
