<template>
  <div class="card">
    <div class="card--image">
      <img :src="loadImg()" />
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class Card extends Vue {
  @Prop() public title!: string;
  @Prop() public fileName!: string;
  @Prop() public body!: string;

  public loadImg(): any {
    return require(`../assets/${this.fileName}`);
  }
}
</script>
<style lang="scss" scoped>
  .card {
    margin: 5px;
    width: 10%;
    border: 1px solid lightgray;
    border-radius: 5px;
    align-items: center;
    display: flex;

    .card--image {
      padding: 5px;
      img {
        width: 100%;
      }
    }
  }
</style>
