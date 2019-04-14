<template>
  <div class="github-activity">
    <a :href="myPageUrl" target="_blank">
      <img :src="activityImageUrl" />
    </a>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class AboutMe extends Vue {
  @Prop() public accountId?: string;

  public get myPageUrl(): string {
    return `https://github.com/${this.accountId}`;
  }

  public get activityImageUrl(): string {
    return `https://grass-graph.moshimo.works/images/${this.accountId}.png`;
  }
}
</script>
<style lang="scss" scoped>
  .github-activity {
    img {
      max-width: 100%;
    }
  }
</style>
