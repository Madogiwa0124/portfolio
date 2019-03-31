<template>
  <div id="app">
    <header>
      <Navbar />
    </header>
    <main>
      main
    </main>
    <footer>
      footer
    </footer>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from './components/HelloWorld.vue';
import Navbar from './components/Navbar.vue';

@Component({
  components: {
    HelloWorld,
    Navbar,
  },
})
export default class App extends Vue {}
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

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  main {
    padding: 5px;
  }
}
</style>
