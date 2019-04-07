<template>
  <div class="modal-card" @click="showModal()">
    <div class="modal-card--image">
      <img :src="loadImg()" />
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class Card extends Vue {
  @Prop() public title?: string;
  @Prop() public body?: string;
  @Prop() public fileName!: string;
  @Prop() public tags?: string[];
  @Prop() public link?: string;

  public loadImg(): any {
    return require(`../assets/${this.fileName}`);
  }

  public showModal(): void {
    const modalProps: any = this.modalProps();
    this.$emit('showModal', modalProps);
  }

  public modalProps(): any {
    return {
      title: this.title,
      fileName: this.fileName,
      body: this.body,
      tags: this.tags,
      link: this.link,
      showModal: true
    };
  }
}
</script>
<style lang="scss" scoped>
  $border-color: lightgray;
  .modal-card {
    cursor: pointer;
    margin: 5px;
    width: 20%;
    @media screen and (min-width:480px) {
      width: 10%;
    }
    border: 1px solid $border-color;
    border-radius: 5px;
    align-items: center;
    display: flex;

    .modal-card--image {
      margin: 0 auto;
      padding: 5px;
      img {
        width: 100%;
      }
    }
  }
  .modal-card:hover {
    transform: scale(1.1,1.1);
    box-shadow: 1px 1px 1px rgba(0, 0, 0, .33);
    transition-duration:0.5s;
  }
</style>
