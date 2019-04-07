<template>
  <div class="my-apps">
    <h2>my Apps</h2>
    <div class="my-apps__collection">
      <Card
        title="MultiTabMarkdownEditor"
        body="タブが使えるMarkdownEditor"
        :tags="['Vue', 'es6', 'Vue-cli']"
        fileName="my_apps/multi_tab_markdown.png"
        link="https://madogiwa0124.github.io/multi-tab-markdown/dist/index.html"
        @showModal="hundleShowModal"
      />
      <Card
        title="dogfeeds"
        body="RssフィードをまとめたRssフィードを作れるWebサービス"
        fileName="my_apps/dogfeeds.png"
        :tags="['ruby', 'rails', 'Vue', 'es6', 'heroku']"
        link="https://dogfeeds.herokuapp.com/"
        @showModal="hundleShowModal"
      />
      <Card
        title="ゴミリマインダー"
        body="ゴミ出しの曜日を通知してくれるLine Bot"
        fileName="my_apps/gomi_remander_bot.png"
        :tags="['ruby', 'LineBot']"
        link="https://github.com/Madogiwa0124/gomi_remainder_bot"
        @showModal="hundleShowModal"
      />
      <Card
        title="Quiq"
        body="作って共有出来るQuiz投稿サービス"
        fileName="my_apps/quiq.jpeg"
        :tags="['ruby', 'rails', 'Vue', 'es6', 'heroku']"
        link="https://quiz-quiq.herokuapp.com/"
        @showModal="hundleShowModal"
      />
      <Card
        title="rails勉強Bot"
        body="railsのメソッドとGithubへのリンクを投稿するTwitterBot"
        fileName="my_apps/rails_study_bot.png"
        :tags="['ruby', 'rails', 'TwitterBot', 'heroku']"
        link="https://twitter.com/rails_study_bot"
        @showModal="hundleShowModal"
      />
      <Card
        title="ruby勉強Bot"
        body="rubyのメソッドとリファレンスマニュアルへのリンクを投稿するTwitterBot"
        fileName="my_apps/ruby_study_bot.png"
        :tags="['ruby', 'Sinatra', 'TwitterBot', 'heroku']"
        link="https://twitter.com/ruby_study_bot"
        @showModal="hundleShowModal"
      />
    </div>
    <div class="my-apps__collection">
      <Card
        title="spp"
        body="special pretty print library"
        fileName="my_apps/spp.png"
        :tags="['ruby', 'ruby gem']"
        link="https://rubygems.org/gems/spp"
        @showModal="hundleShowModal"
      />
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Card from './Card.vue';

@Component({
  components: {
    Card,
  },
})
export default class MyApps extends Vue {
  public hundleShowModal(modalProps: any): void {
    this.$emit('showModal', modalProps);
  }
}
</script>
<style lang="scss" scoped>
  .my-apps {
    .my-apps__collection {
      display: flex;
    }
  }
</style>
