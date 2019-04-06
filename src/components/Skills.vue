<template>
  <div class="skills">
    <h2>Skills</h2>
    <h3 class="skills--title">in work</h3>
    <div class="skills__collection">
      <Card fileName="ruby.png" />
      <Card fileName="rails.png" />
      <Card fileName="rspec.png" />
      <Card fileName="sidekiq.png" />
      <Card fileName="es6.png" />
      <Card fileName="vue.png" />
    </div>
    <div class="skills__collection">
      <Card fileName="mysql.png" />
      <Card fileName="git.png" />
      <Card fileName="github.png" />
      <Card fileName="docker.png" />
      <Card fileName="esa.png" />
    </div>
    <h3 class="skills--title">in hoby</h3>
    <div class="skills__collection">
      <Card fileName="ionic.png" />
      <Card fileName="typescript.png" />
      <Card fileName="firestore.png" />
      <Card fileName="postgresql.png" />
      <Card fileName="heroku.png" />
      <Card fileName="circleci.png" />
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Card from './Card.vue';

@Component({
  components: {
    Card,
  },
})
export default class AboutMe extends Vue {
}
</script>
<style lang="scss" scoped>
  .skills {
    .skills__collection {
      display: flex;
    }
  }
</style>
