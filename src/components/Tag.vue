<template>
  <span class="tags">
    {{ name }}
  </span>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class ModalCard extends Vue {
  @Prop() public name!: string;
}
</script>
<style lang="scss" scoped>
  $bg-color: #42B983;
  $color: #FFFFFF;

  .tags {
    color: $color;
    margin: 2px;
    padding: 3px;
    border-radius: 2px;
    background-color: $bg-color;
  }
</style>
