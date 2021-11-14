<template>
  <div>
    <Hero :subtitle="hero.subtitle" :title="hero.title" :text="hero.text"></Hero>
    <div class="container py-4">
      <p v-if="$fetchState.pending">Fetching articles...</p>
      <p v-else-if="$fetchState.error">An error occurred :(</p>
      <div v-else class="blog-container row">
        <h4>Featured Posts</h4>
        <BlogCarousel :articles="this.articles"></BlogCarousel>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      articles: [],
      hero: {
        title: 'Blog slogan goes here.',
        subtitle: 'Welcome to my Blog',
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
      }
    }
  },
  async fetch() {
    this.articles = await fetch(
      'https://6141b2f5357db50017b3dc1a.mockapi.io/api/v1/Articles'
    ).then(res => res.json())
  },
  layout: "app",
};
</script>
