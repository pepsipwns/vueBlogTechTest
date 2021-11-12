<template>
  <div class="container">
    <h1 v-if="error.statusCode === 404"> {{error.statusCode}} - Page not found</h1>
    <h1 v-else>{{error.statusCode}} - An error occurred</h1>
    <NuxtLink to="/">Home page</NuxtLink>
  </div>
</template>

<script>
export default {
  props: ['error'],
  layout: 'blog'
}
</script>