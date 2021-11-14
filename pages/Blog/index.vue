<template>
  <div>
    <Hero :searchArticles="searchArticles" :searchValue="searchValue" subtitle="Wonderful Blog" title="My Blog" text="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."></Hero>
    <div class="container">
      <div class="row pt-3">
        <div class="col-5 d-flex justify-content-center flex-column">
        </div>
      </div>
      <p v-if="$fetchState.pending">Fetching articles...</p>
      <p v-else-if="$fetchState.error">An error occurred :(</p>
      <div v-else class="blog-container row">
        <BlogCard
          v-for="(article, i) of articles"
          :key="i"
          :createdAt="article.createdAt"
          :author="article.author"
          :image="article.image"
          :title="article.title"
          :intro="article.intro"
          :text="article.text"
          :id="article.id"
          class="col"
        ></BlogCard>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      articles: [],
      searchValue: null
    }
  },
  methods: {
    searchArticles: function (search) {
      console.log('searching: ' + search);
      console.log('link: ' + 'https://6141b2f5357db50017b3dc1a.mockapi.io/api/v1/Articles?search=' + search);
      fetch(
        'https://6141b2f5357db50017b3dc1a.mockapi.io/api/v1/Articles?search=' + search
      )
        .then(response => response.json())
        .then(data => {
          this.articles = data;
          console.log(data);
        });
    }
  },
  async fetch() {
    this.articles = await fetch(
      'https://6141b2f5357db50017b3dc1a.mockapi.io/api/v1/Articles?page=1&limit=9'
    ).then(res => res.json())
  },
  layout: "app",
  // middleware({ redirect }) {
  //   return redirect("301", "/Blog/page/1");
  //   }
};
</script>
