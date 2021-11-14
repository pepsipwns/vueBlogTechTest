<template>
  <div>
    <Hero :subtitle="article.author" :title="article.title" :text="article.intro" :image="article.image"></Hero>
    <div class="container">
      <p class="py-5 px-3">{{ article.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      article: {}
    }
  },
  async fetch() {
    this.article = await fetch(
      'https://6141b2f5357db50017b3dc1a.mockapi.io/api/v1/Articles/' + this.$route.params.id
    ).then(res => res.json())
  },
  layout: "app",
};
</script>
