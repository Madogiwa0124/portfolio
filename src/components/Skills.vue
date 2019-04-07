<template>
  <div class="skills">
    <h2>Skills</h2>
    <h3 class="skills--title">in work</h3>
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
    </div>
    <h3 class="skills--title">in hoby</h3>
    <div class="skills__collection">
      <Card fileName="skills/ionic.png" />
      <Card fileName="skills/typescript.png" />
      <Card fileName="skills/firestore.png" />
      <Card fileName="skills/postgresql.png" />
      <Card fileName="skills/heroku.png" />
      <Card fileName="skills/circleci.png" />
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
      flex-wrap: wrap;
    }
  }
</style>
