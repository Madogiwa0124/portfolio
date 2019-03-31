<template>
  <div class="navbar">
    <ul class="navbar__list">
      <li class="navbar__list--brand">
        <a href="/">Madogiwa's Portfolio</a>
      </li>
      <NavbarItem
        v-for="(item, index) in items"
        :key="index"
        :href="item.href"
        :title="item.title"
        :isActive="item.isActive"
        @activate="hundleOnItemActivate(index)"
      />
    </ul>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import NavbarItem from './NavbarItem.vue';

@Component({
  components: { NavbarItem },
})
export default class Navbar extends Vue {
  public items: any[] = [
    { href: '#about-me', title: 'Abount me', isActive: false },
    { href: '#skills', title: 'Skills', isActive: false },
    { href: '#contact', title: 'Contact', isActive: false },
    { href: '#my-apps', title: 'My apps', isActive: false },
    { href: '#blog', title: 'Blog', isActive: false },
  ];

  public hundleOnItemActivate(index: number): void {
    this.items.forEach((item) => { item.isActive = false; });
    this.items[index].isActive = true;
  }
}
</script>
<style lang="scss" scoped>
  $bg-color: #333;
  $brand-color: #FFFFFF;

  .navbar{
    .navbar__list {
      .navbar__list--brand {
        float: left;
        a {
          display: block;
          color: $brand-color;
          font-weight: bold;
          text-align: center;
          padding: 14px 16px;
          text-decoration: none;
        }
      }
      list-style-type: none;
      margin: 0;
      padding: 0;
      overflow: hidden;
      background-color: $bg-color;
    }
  }
</style>
