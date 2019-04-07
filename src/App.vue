<template>
  <div id="app">
    <header>
      <Navbar />
    </header>
    <AboutMe />
    <main>
      <Skills />
      <MyApps @showModal="handleShowModal" />
      <Modal
        :title="state.currentModalProps.title"
        :body="state.currentModalProps.body"
        :fileName="state.currentModalProps.fileName"
        :link="state.currentModalProps.link"
        :tags="state.currentModalProps.tags"
        :showModal="state.currentModalProps.showModal"
        @closeModal="handleCloseModal"
      />
    </main>
    <footer>
      footer
    </footer>
  </div>
</template>

<script lang="ts">
import store from './store';
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from './components/HelloWorld.vue';
import Navbar from './components/Navbar.vue';
import AboutMe from './components/AboutMe.vue';
import Skills from './components/Skills.vue';
import MyApps from './components/MyApps.vue';
import Modal from './components/Modal.vue';

@Component({
  components: {
    HelloWorld,
    Navbar,
    AboutMe,
    Skills,
    MyApps,
    Modal,
  },
})
export default class App extends Vue {
  public state: any = store.state;

  public handleShowModal(modalProps: any): void {
    this.state.currentModalProps = modalProps;
  }
  public handleCloseModal(): void {
    this.state.currentModalProps.showModal = false;
  }
}
</script>

<style lang="scss">
html {
  margin: 0px;
  padding: 0px;
}

body {
  margin: 0px;
  padding: 0px;
}

main {
  margin: 2em;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  main {
    padding: 5px;
  }
}
</style>
