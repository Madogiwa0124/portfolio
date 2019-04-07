<template>
  <div class="skills" id="skills">
    <h2 class="skills--title">Skills</h2>
    <h3 class="skills--subtitle">in work</h3>
    <div class="skills__collection">
      <Card fileName="skills/ruby.png" />
      <Card fileName="skills/rails.png" />
      <Card fileName="skills/rspec.png" />
      <Card fileName="skills/sidekiq.png" />
      <Card fileName="skills/es6.png" />
      <Card fileName="skills/vue.png" />
      <Card fileName="skills/mysql.png" />
      <Card fileName="skills/git.png" />
      <Card fileName="skills/github.png" />
      <Card fileName="skills/docker.png" />
      <Card fileName="skills/esa.png" />
      <Card fileName="skills/circleci.png" />
    </div>
    <h3 class="skills--subtitle">in hoby</h3>
    <div class="skills__collection">
      <Card fileName="skills/ionic.png" />
      <Card fileName="skills/typescript.png" />
      <Card fileName="skills/firestore.png" />
      <Card fileName="skills/postgresql.png" />
      <Card fileName="skills/heroku.png" />
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
    .skills--title {
      border-left: 2px solid #4CAF50;
      padding-left: 15px;
    }
    .skills__collection {
      display: flex;
      flex-wrap: wrap;
    }
  }
</style>
