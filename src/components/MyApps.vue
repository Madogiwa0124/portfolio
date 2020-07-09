<template>
  <div class="my-apps" id="my-apps">
    <h2 class="my-apps--title">My apps</h2>
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
      <Card
        title="spp"
        body="special pretty print library"
        fileName="my_apps/spp.png"
        :tags="['ruby', 'ruby gem']"
        link="https://rubygems.org/gems/spp"
        @showModal="hundleShowModal"
      />
      <Card
        title="CronConfigParser"
        body="parse the cron configuration for readability"
        fileName="my_apps/cron_config_parser.png"
        :tags="['ruby', 'ruby gem']"
        link="https://rubygems.org/gems/cron_config_parser"
        @showModal="hundleShowModal"
      />
      <Card
        title="Makanai"
        body="simple web application framework for learning."
        fileName="my_apps/makanai.png"
        :tags="['ruby', 'ruby gem']"
        link="https://rubygems.org/gems/makanai"
        @showModal="hundleShowModal"
      />
      <Card
        title="ActiveRecordJsonExplain"
        body="This gem extends ActiveRecord::Relation#explain to make it possible to get EXPLAIN in JSON format."
        fileName="my_apps/active_record_json_explain.png"
        :tags="['ruby', 'ruby gem']"
        link="https://rubygems.org/gems/active_record_json_explain"
        @showModal="hundleShowModal"
      />
      <Card
        title="TravelToJavascript"
        body="provides a helper `travel_to_javascript` that locks time in javascript."
        fileName="my_apps/travel_to_javascript.png"
        :tags="['ruby', 'ruby gem']"
        link="https://rubygems.org/gems/travel_to_javascript"
        @showModal="hundleShowModal"
      />
      <Card
        title="TickTube"
        body="YouTubeの動画をスワイプして閲覧できるViewer"
        fileName="my_apps/ticktube.png"
        :tags="['Vue', 'TypeScript', 'es6', 'YouTube Date API']"
        link="https://madogiwa0124.github.io/ticktube/"
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
    .my-apps--title {
      border-left: 2px solid #4CAF50;
      padding-left: 15px;
    }
    .my-apps__collection {
      display: flex;
      flex-wrap: wrap;
    }
  }
</style>
