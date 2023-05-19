<template lang="pug">
AppHeader(:currentIndex="0")
.works 
  h1.title Work
  .feature__box(v-for="work in works" :key="work.title")
    img.feature__img(:src="work.img")
    .feature__right 
      .feature__title {{ work.title }}
      .feature__info
        .feature__year {{ work.year }}
        .feature__type {{ work.type }}
      .feature__text {{ work.text }}
AppFooter
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import AppFooter from '@/components/AppFooter.vue'
import json from '@/assets/data/works.json'

export default {
  name: "WorksView",
  components: {
    AppHeader,
    AppFooter,
  },
  data() {
    return {
      works: json,
    }
  }
}
</script>

<style lang="sass" scoped>
.works 
  padding: 5rem
</style>