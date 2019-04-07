<template>
  <div class="blog-card" @click="redirect_to(link)">
    <h3 class="blog-card--title" :title="title">
      {{ title }}
    </h3>
    <img :src="thumbnail">
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class BlogCard extends Vue {
  @Prop() public title?: string;
  @Prop() public thumbnail?: string;
  @Prop() public link?: string;

  public redirect_to(url: string) {
    location.href=url;
  }
}
</script>
<style lang="scss" scoped>
  .blog-card {
    width: 45%;
    margin: 5px;
    border-bottom: 1px #4CAF50 solid;
    cursor: pointer;

    .blog-card--title {
      margin: 5px;
      overflow: hidden;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 2;
    }

    img {
      width: 100%;
      max-height: 300px;
    }
  }
</style>
