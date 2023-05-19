<template lang="pug">
.app-posts
  .header
    .caption Recent posts
    span.view(@click="viewAll = !viewAll") View all
  .posts
    .post(v-for="(post, index) in posts" :key="post.title" v-show="viewAll || index<2")
      h1.post__title {{ post.title }}
      .post__header 
        .post__date {{ new Date(post.date).toDateString() }}
        .vl
        .post__theme {{ post.theme }}
      p.post__text {{ post.text }}
</template>

<script>
import json from '@/assets/data/posts.json'
export default {
  name: "AppPosts",
  data() {
    return {
      posts: json,
      viewAll: false,
    }
  }
}
</script>

<style lang="sass" scoped>
.app-posts
  padding: 5rem 22rem 5rem 8rem
  background-color: #EDF7FA

  @media(max-width: 1000px)
    padding: 5rem

.header
  display: flex
  justify-content: space-between
  font-family: 'Heebo Medium'
  padding-bottom: 1rem

.caption  
  font-size: 1.3rem
.view
  cursor: pointer
  color: #24A9CA
  
.posts
  display: grid
  grid-template-columns: 1fr 1fr
  gap: 2rem

  @media(max-width: 1000px)
    grid-template-columns: 1fr

.post
  background-color: #fff
  padding: 2rem
  border-radius: 10px

  &__header
    display: flex
    gap: 1rem
    padding: 1.5rem 0 1rem
</style>