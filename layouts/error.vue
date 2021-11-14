<template>
  <div>
    <Hero :subtitle="error.statusCode" :title="error.statusCode === 404 ? 'Page not found' : 'An error occurred'"></Hero>
    <NuxtLink to="/" class="text-decoration-none"><h1 class="container px-3 py-3">Back to Home</h1></NuxtLink>
  </div>
</template>

<script>
export default {
  props: ['error'],
  layout: 'blog'
}
</script>