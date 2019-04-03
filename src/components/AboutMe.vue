<template>
  <div class="aboutme">
    <div class="aboutme__content">
      <h3 class="aboutme__content--title">Madogiwa</h3>
      <p class="aboutme__content--body">
        都内のITベンチャーで働く窓際Webプログラマーです👩‍💻
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
