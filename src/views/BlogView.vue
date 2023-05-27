<template lang="pug">
AppHeader(:currentIndex="1")
.blog 
  h1.title Blog
  RouterLink.post(v-for="post in posts" :key="post.title"
  :to="`/post/${post.title}`") 
    h1.post__title {{ post.title }}
    .post__header 
      .post__date {{ new Date(post.date).toDateString() }}
      .vl
      .post__theme {{ post.theme }}
    p.post__text {{ post.text }}
AppFooter
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import AppFooter from '@/components/AppFooter.vue'
import json from '@/assets/data/posts.json'

export default {
  name: "BlogView",
  components: {
    AppHeader,
    AppFooter,
  },
  data() {
    return {
      posts: json,
    }
  }
}
</script>

<style lang="sass" scoped>
.blog
  padding: 5rem

.title
  padding: 2rem 0

.post

  padding: 2rem 0
  border-radius: 10px
  &__header
    display: flex
    gap: 1rem
    padding: 1.5rem 0 1rem
  &__text
    padding: 1rem 0
</style>