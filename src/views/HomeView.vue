<template lang="pug">
AppHeader
AppCard
main 
  AppPosts
  AppFeatured
AppFooter
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import AppFooter from '@/components/AppFooter.vue'
import AppCard from '@/components/AppCard.vue'
import AppPosts from '@/components/AppPosts.vue'
import AppFeatured from '@/components/AppFeatured.vue'

export default {
  name: "HomeView",
  components: {
    AppHeader,
    AppFooter,
    AppCard,
    AppPosts,
    AppFeatured,
  },
  data() {
    return {

    }
  }
}
</script>

<style lang="sass">
.vl
  border-left: 1px solid
  height: 20px
</style>
