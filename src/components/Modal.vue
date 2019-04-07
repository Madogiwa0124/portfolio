<template>
  <transition name="modal" v-if="showModal">
    <div class="modal-mask">
      <div class="modal-wrapper" @click="closeModal()">
        <div class="modal-container">
          <div class="modal-header">
            <div name="header">
              <h3>{{ title }}</h3>
            </div>
          </div>
          <div class="modal-body">
            <img :src="loadImg()" />
            <div name="body">
              {{ body }}<br>
              <a :href="link" target="_blank">{{ link }}</a>
            </div>
          </div>
          <div class="modal-footer">
            <div name="footer">
              <Tag v-for="(tag, index) in tags" :key="index" :name="tag" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';
import Tag from './Tag.vue';

@Component({
  components: { Tag },
})

export default class Modal extends Vue {
  @Prop() public title!: string;
  @Prop() public body!: string;
  @Prop() public fileName!: string;
  @Prop() public tags!: string[];
  @Prop() public link!: string;
  @Prop() public showModal: boolean = false;

  public closeModal(): void {
    this.$emit('closeModal');
  }

  public loadImg(): any {
    return require(`../assets/${this.fileName}`);
  }
}
</script>
<style lang="scss" scoped>
  $title-color: #42B983;
  $bg-color: #FFFFFF;
  $shadow-color: rgba(0, 0, 0, .33);
  $mask-bg-color: rgba(0, 0, 0, .5);

  .modal-mask {
    position: fixed;
    z-index: 10;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: $mask-bg-color;
    display: table;
    transition: opacity .3s ease;
  }

  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;
  }

  .modal-container {
    width: 250px;
    @media screen and (min-width:480px) {
      width: 300px;
    }
    margin: 0px auto;
    padding: 10px 10px;
    background-color: $bg-color;
    border-radius: 2px;
    box-shadow: 0 2px 8px shadow-color;
    transition: all .3s ease;
  }

  .modal-header h3 {
    margin-top: 0;
    color: $title-color;
  }

  .modal-body {
    margin: 20px 0;
    word-wrap: break-word;
    img {
      width: 100%;
    }
  }

  .modal-enter {
    opacity: 0;
  }

  .modal-leave-active {
    opacity: 0;
  }

  .modal-enter .modal-container,
  .modal-leave-active .modal-container {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
  }
</style>
