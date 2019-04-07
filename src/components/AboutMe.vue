<template>
  <div class="aboutme">
    <div class="aboutme__content">
      <h3 class="aboutme__content--title">Madogiwa</h3>
      <img src="https://pbs.twimg.com/profile_images/1060339222085697536/2f3ffaLs_400x400.jpg">
      <p class="aboutme__content--body">
        都内のIT企業で働く窓際Webプログラマーです👩‍💻
        <ul class="contacts">
          <li>
            Twitter:
            <a href="https://twitter.com/Madogiwa_Boy" target="_blank">
              @Madogiwa_Boy
            </a>
          </li>
          <li>
            Github:
            <a href="https://github.com/Madogiwa0124" target="_blank">
              @Madogiwa0124
            </a>
          </li>
        </ul>
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
    background-color: #F6F6F6;

    .aboutme__content {
      text-align: center;
      padding: 20px;

      img {
        border-radius: 200px;
        max-width: 20%;
      }

      .aboutme__content--title {
        margin: 0px;
      }

      .aboutme__content--body {
        margin: 0px;
        .contacts {
          list-style: none;
          text-align: center;
          padding: 0px;
        }
      }
    }
  }
</style>
