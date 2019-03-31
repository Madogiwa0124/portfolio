<template>
  <li class="navbar__list__item" :class="{ active: isActive }">
    <a
      :href="href"
      @click="activate"
    >
      {{title}}
    </a>
  </li>
</template>
<script lang="ts">
import { Component, Prop, Vue, Watch } from 'vue-property-decorator';

@Component
export default class NavbarItem extends Vue {
  @Prop() public index!: number;
  @Prop() public href!: string;
  @Prop() public title!: string;
  @Prop() public isActive!: boolean;

  public activate(): void {
    this.$emit('activate', this.index);
  }
}
</script>
<style lang="scss" scoped>
  $color: #FFFFFF;
  $hover-item-bg-color: #111;
  $active-item-bg-color: #4CAF50;
  $active-item-color: #FFFFFF;

  .navbar__list__item {
    float: left;
    a {
      display: block;
      color: $color;
      text-align: center;
      padding: 14px 16px;
      text-decoration: none;
    }
    a:hover {
      background-color: $hover-item-bg-color;
    }
    &.active {
      background-color: $active-item-bg-color;
      color: $active-item-color;
    }
  }
</style>
