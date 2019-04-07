<template>
  <div class="blogs" id="blogs">
    <h2 class="blogs--title">Blog</h2>
    <div class="blogs__items">
      <BlogCard
        v-for="(blog, index) in blogs" :key="index"
        :title="blog.title"
        :thumbnail="blog.thumbnail"
        :link="blog.link"
      />
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';
import BlogCard from './BlogCard.vue';
import axios from 'axios';

const BLOGS_LIMIT = 4;

@Component ({
  components: { BlogCard },
})
export default class Blogs extends Vue {
  @Prop() public endpoint!: string;

  public blogs: object[] = [];
  public parser: DOMParser = new DOMParser();

  public created() {
    axios.get(this.endpoint).then((res)  => {
      const rssDom = this.parser.parseFromString(res.data, 'text/xml');
      this.buildRssBlogItems(rssDom);
    });
  }

  private buildRssBlogItems(dom: Document): void {
    dom.querySelectorAll('item').forEach((item) => {
      const itemDom = this.parser.parseFromString(item.innerHTML, 'text/html');
      this.blogs.push(this.blogProps(itemDom));
    });
    this.blogs = this.blogs.slice(0, BLOGS_LIMIT);
  }

  private blogProps(dom: Document): object  {
    const thumbnail = dom.querySelector('enclosure')!.getAttribute('url');
    const title = dom.querySelector('title')!.text;
    const link = dom.querySelector('body')!.firstChild!.textContent!.trim();
    return { title, thumbnail, link };
  }
}
</script>
<style lang="scss" scoped>
  .blogs {
    .blogs--title {
      border-left: 2px solid #4CAF50;
      padding-left: 15px;
    }

    .blogs__items {
      display: flex;
      flex-wrap: wrap;
    }
  }
</style>
