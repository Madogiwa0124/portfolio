<template>
  <div class="aboutme">
    <h2 class="aboutme--title">About Me</h2>
    <div class="aboutme__content">
      <h4 class="aboutme__content--title">自己紹介</h4>
      <p class="aboutme__content--body">
        都内の某ヘルステック系企業で働く窓際Railsエンジニアです👩‍💻
      </p>
      <h4 class="aboutme__content--title">好きなもの</h4>
      <p class="aboutme__content--body">
        web漫画、プロレス、webサービス作ること🙌
      </p>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class AboutMe extends Vue {
}
</script>
<style lang="scss" scoped>
  .aboutme{
    .aboutme__content {
      .aboutme__content--title {
        margin: 10px;
      }
      .aboutme__content--body {
        margin: 10px;
      }
    }
  }
</style>
